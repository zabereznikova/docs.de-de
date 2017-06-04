---
title: "How to: Continue a Windows Service (Visual Basic) | Microsoft Docs"
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
  - "ServiceController.Continue"
helpviewer_keywords: 
  - "Windows Service applications, pausing"
  - "pausing Windows Service applications"
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
caps.latest.revision: 16
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 16
---
# How to: Continue a Windows Service (Visual Basic)
In diesem Beispiel wird mit der <xref:System.ServiceProcess.ServiceController>\-Komponente der IIS\-Verwaltungsdienst auf dem lokalen Computer fortgesetzt.  
  
## Beispiel  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Dieses Codebeispiel ist auch als IntelliSense\-Codeausschnitt verfügbar.  Das Beispiel befindet sich in der Codeausschnittauswahl unter **Windows\-Betriebssystem \> Windows\-Dienste**.  Weitere Informationen finden Sie unter [Codeausschnitte](../Topic/Code%20Snippets.md).  
  
## Kompilieren des Codes  
 Dieses Beispiel setzt Folgendes voraus:  
  
-   Ein Projektverweis zu System.serviceprocess.dll.  
  
-   Zugriff auf die Member des <xref:System.ServiceProcess>\-Namespaces.  Fügen Sie eine `Imports`\-Anweisung hinzu, wenn der Code keine vollqualifizierten Membernamen enthält.  Weitere Informationen finden Sie unter [Imports Statement \(.NET Namespace and Type\)](../../../ocs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## Robuste Programmierung  
 Die <xref:System.ServiceProcess.ServiceController.MachineName%2A>\-Eigenschaft der <xref:System.ServiceProcess.ServiceController>\-Klasse ist standardmäßig der lokale Computer.  Um auf Windows\-Dienste auf einem anderen Computer zu verweisen, ändern Sie die <xref:System.ServiceProcess.ServiceController.MachineName%2A>\-Eigenschaft in den Namen des betreffenden Computers.  
  
 Sie können die <xref:System.ServiceProcess.ServiceController.Continue%2A>\-Methode in einem Dienst erst aufrufen, wenn der Dienstcontrollerstatus <xref:System.ServiceProcess.ServiceControllerStatus> lautet.  
  
 Unter den folgenden Bedingungen kann eine Ausnahme ausgelöst werden:  
  
-   Der Dienst kann nicht fortgesetzt werden.  \(<xref:System.InvalidOperationException>\)  
  
-   Fehler beim Zugriff auf eine System\-API.  \(<xref:System.ComponentModel.Win32Exception>\)  
  
## .NET Framework-Sicherheit  
 Die Steuerung von Diensten auf dem Computer kann eingeschränkt werden, indem Sie die <xref:System.ServiceProcess.ServiceControllerPermissionAccess>\-Enumeration verwenden, um Berechtigungen in der <xref:System.ServiceProcess.ServiceControllerPermission>\-Klasse festzulegen.  
  
 Der Zugriff auf Dienstinformationen kann eingeschränkt werden, indem Sie die <xref:System.Security.Permissions.PermissionState>\-Enumeration verwenden, um Berechtigungen in der <xref:System.Security.Permissions.SecurityPermission>\-Klasse festzulegen.  
  
## Siehe auch  
 <xref:System.ServiceProcess.ServiceController>   
 <xref:System.ServiceProcess.ServiceControllerStatus>   
 [How to: Pause a Windows Service \(Visual Basic\)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)