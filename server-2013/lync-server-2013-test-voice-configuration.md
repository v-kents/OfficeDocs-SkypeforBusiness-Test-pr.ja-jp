﻿---
title: 'Lync Server 2013: Test voice configuration'
TOCTitle: Test voice configuration
ms:assetid: 574794a3-cb30-4762-bb62-3a68574f05e9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn725208(v=OCS.15)
ms:contentKeyID: 62335954
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Test voice configuration in Lync Server 2013

 

_**トピックの最終更新日:** 2015-03-09_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Verification schedule</p></td>
<td><p>Monthly</p></td>
</tr>
<tr class="even">
<td><p>Testing tool</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permissions required</p></td>
<td><p>When run locally using the Lync Server 管理シェル, users must be members of the RTCUniversalServerAdmins security group.</p>
<p>When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceTestConfiguration cmdlet. To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceTestConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


## Description

Lync Server includes several Windows PowerShell cmdlets (such as Test-CsVoiceRoute and Test-CsVoicePolicy, Test-CsTrunkConfiguration) that enable you to verify that the individual pieces of your Enterprise Voice infrastructure – voice routes, voice policies, SIP trunks – are working as expected.

While it’s important with Enterprise Voice that all the individual pieces work: it’s possible to have a valid voice route, a valid voice policy, and a valid SIP trunk, but still have users unable to make or receive phone calls. Because of that, Lync Server also provides the ability to create voice test configurations. Voice test configurations represent common Enterprise Voice scenarios: you can specify such things as a voice route, a voice policy, and a dial plan, and then verify that those individual items are work able to work together to provide phone service. In addition, you can validate your expectations in a given scenario. For example, suppose that you expect that the combination of dial plan A and voice policy B would result in calls being routed over voice route C. You can enter voice route C as the ExpectedRoute. When you run the test, if voice route C is not employed then the test will be marked as having failed.

## Running the test

Before testing Voice configuration collections using Windows PowerShell, you must first use the Get-CsVoiceTestConfiguration cmdlet to retrieve an instance of these configuration settings. That instance must then be piped to the Test-CsVoiceTestConfiguration. For example:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

To validate all the voice test configuration settings at the same time, use this command instead:

`Get-CsVoiceTestConfiguration | Test-CsVoiceTestConfiguration`

For more information, see the Help documentation for the Test-CsVoiceTestConfiguration cmdlet.

## Determining success or failure

The Test-CsVoiceTestConfiguration cmdlet reports whether a test failed or succeeded, and provides additional information about each successful test, such as the translation rule, voice route, and PSTN usage used to complete the task:

Result:             Success

TranslatedNumber:   +15551234

MatchingRule:       Description=;Pattern=^(\\d{4})$;Translation=+1\\d;Name=Test;IsInternalExtension=False

FirstMatchingRoute: site:Redmond

MatchingUsage:      Local

If the test fails then the result is reported as Fail:

Result:             Fail

TranslatedNumber:   

FirstMatchingRoute:

MatchingUsage:      

## Reasons why the test might have failed

Because voice test configuration testing tests several different items – including voice policies, dial plans, voice routes, and so on – there are several different factors that could result in a failed test. If a test fails, your first step should be to review the configuration settings themselves by using the Get-CsVoiceTestConfiguration cmdlet:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration"`

If the settings seem to be configured correctly, re-run the test while including the Verbose parameter:

`Get-CsVoiceTestConfiguration -Identity "RedmondVoiceTestConfiguration" | Test-CsVoiceTestConfiguration`

The Verbose parameter will provide a step-by-step account of each action taken by Test-CsVoiceTestConfiguration as shown in this example:

VERBOSE: Loading dial plan: "Global"

VERBOSE: Loading voice policy: "RedmondDialPlan"

This step-by-step account might provide a useful clue as to where the test actually failed. If not, you can then use other Windows PowerShell cmdlets (such as Test-CsVoicePolicy) and methodically begin to verify the individual components that are included in the voice test configuration settings.

In addition to that, be aware that it’s possible for a test to be able to route a call and yet still be marked as a failure; that can occur if you enter values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage, and any of those expectations are not met. For example, suppose that you enter voice route C as your expected voice route, but the test actually completes the call using voice route D. In that case the test will be marked as Failed because the expected voice route was not used. If a test fails, you might remove the values for ExpectedRoute, ExpectedTranslatedNumber, and ExpectedUsage and then re-run the test. That will help you determine whether the failure was because the call couldn't be completed, or because you expect one thing and actually received another.

## 関連項目

#### その他のリソース

[Test-CsVoiceTestConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsVoiceTestConfiguration)

