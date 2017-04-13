---
title: "How to: Pause a Windows Service (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceController.Pause"
helpviewer_keywords: 
  - "Windows Service applications, pausing"
  - "pausing Windows Service applications"
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 15
---
# How to: Pause a Windows Service (Visual Basic)
In diesem Beispiel wird mithilfe der <xref:System.ServiceProcess.ServiceController>\-Komponente der IIS\-Verwaltungsdienst auf dem lokalen Computer angehalten.  
  
## Beispiel  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 Dieses Codebeispiel ist auch als IntelliSense\-Codeausschnitt verfügbar.  Das Beispiel befindet sich in der Codeausschnittauswahl unter **Windows\-Betriebssystem \> Windows\-Dienste**.  Weitere Informationen finden Sie unter [Codeausschnitte](../Topic/Code%20Snippets.md).  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein Projektverweis zu System.serviceprocess.dll.  
  
-   Zugriff auf die Member des <xref:System.ServiceProcess>\-Namespaces.  Fügen Sie eine `Imports`\-Anweisung hinzu, wenn der Code keine vollqualifizierten Membernamen enthält.  Weitere Informationen finden Sie unter [Imports Statement \(.NET Namespace and Type\)](../../../ocs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## Robuste Programmierung  
 Die <xref:System.ServiceProcess.ServiceController.MachineName%2A>\-Eigenschaft der <xref:System.ServiceProcess.ServiceController>\-Klasse ist standardmäßig der lokale Computer.  Um auf Windows\-Dienste auf einem anderen Computer zu verweisen, ändern Sie die <xref:System.ServiceProcess.ServiceController.MachineName%2A>\-Eigenschaft in den Namen des betreffenden Computers.  
  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Dienst kann nicht angehalten werden.  \([InvalidOperationException\-Klasse](frlrfSystemInvalidOperationExceptionClassTopic)\)  
  
-   Fehler beim Zugriff auf eine System\-API.  \([Win32Exception\-Klasse](frlrfSystemComponentModelWin32ExceptionClassTopic)\)  
  
## .NET Framework-Sicherheit  
 Die Steuerung von Diensten auf dem Computer kann eingeschränkt werden, indem Sie die [ServiceControllerPermissionAccess\-Enumeration](frlrfSystemServiceProcessServiceControllerPermissionAccessClassTopic) verwenden, um Berechtigungen in der [ServiceControllerPermission\-Klasse](frlrfSystemServiceProcessServiceControllerPermissionClassTopic) festzulegen.  
  
 Der Zugriff auf Dienstinformationen kann eingeschränkt werden, indem Sie die [PermissionState\-Enumeration](frlrfSystemSecurityPermissionsPermissionStateClassTopic) verwenden, um Berechtigungen in der [SecurityPermission\-Klasse](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic) festzulegen.  
  
## Siehe auch  
 <xref:System.ServiceProcess.ServiceController>   
 <xref:System.ServiceProcess.ServiceControllerStatus>   
 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>   
 [How to: Continue a Windows Service \(Visual Basic\)](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)