---
title: 'Lync Server 2013: Modify a voice route'
ms.reviewer: 
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
---

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# Modify a voice route in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Topic Last Modified:** 2012-11-01_

This topic explains how to edit a voice route. To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).

<div>

## To modify a voice route

1.  Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel. For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  In the left navigation bar, click **Voice Routing**, and then click **Route**.

4.  On the **Route** page, use either of the following methods to modify a voice route:
    
      - Click a voice route name, click **Edit**, and then click **Show details**.
    
      - Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.

5.  In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.

6.  (Optional) In the **Description** field, type in additional descriptive information for the voice route.

7.  To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.
    
      - To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:
        
          - **Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed). For example, type **+425** and then click **Add**. Repeat this for each prefix value that you want to include in the route.
        
          - **Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**. Type in one or more values for the matching patterns that you do *not* want this route to accommodate. For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.
    
      - To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied. For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).

8.  Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.

9.  To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.
    
    <div>
    

    > [!NOTE]  
    > If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.

    
    </div>

10. To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.
    
    <div>
    

    > [!NOTE]  
    > To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.<BR>To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.

    
    </div>

11. Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.
    
    <div>
    

    > [!NOTE]  
    > In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant. However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup. (Lync Server traverses the list from the top down.)

    
    </div>

12. (Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.
    
    <div>
    

    > [!NOTE]  
    > You can save a voice route that does not yet pass the test and then reconfigure it later. For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.

    
    </div>

13. Click **OK**.

14. On the **Route** page, click **Commit**, and then click **Commit all**.
    
    <div>
    

    > [!NOTE]  
    > Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change. For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.

    
    </div>

</div>

<div>

## See Also


[Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[View PSTN usage records in Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Publish pending changes to the voice routing configuration in Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[Test voice routing in Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

