---
title: 'Gewusst wie: Anhalten von Windows-Diensten (Visual Basic)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
f1_keywords: ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: d44358d3f76f50a06ede5e7d720f4f48d80893de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a>Gewusst wie: Anhalten von Windows-Diensten (Visual Basic)
Dieses Beispiel verwendet die <xref:System.ServiceProcess.ServiceController> Komponente so halten Sie die IIS-Verwaltungsdienst auf dem lokalen Computer an.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. In der Codeausschnittauswahl befindet sich im **Windows-Betriebssystem > Windows-Dienste**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein Projektverweis zu System.serviceprocess.dll.  
  
-   Zugriff auf die Member des <xref:System.ServiceProcess>-Namespace Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die <xref:System.ServiceProcess.ServiceController.MachineName%2A> Eigenschaft von der <xref:System.ServiceProcess.ServiceController> Klasse ist der lokale Computer standardmäßig. Um Windows-Dienste auf einem anderen Computer verweisen, ändern Sie die <xref:System.ServiceProcess.ServiceController.MachineName%2A> -Eigenschaft auf den Namen des betreffenden Computers.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Dienst kann nicht angehalten werden. (<xref:System.InvalidOperationException>)  
  
-   Beim Zugreifen auf eine System-API ist ein Fehler aufgetreten. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Die Steuerung von Diensten auf dem Computer kann eingeschränkt werden, mithilfe der <xref:System.ServiceProcess.ServiceControllerPermissionAccess> zum Festlegen von Berechtigungen der <xref:System.ServiceProcess.ServiceControllerPermission>.  
  
 Zugriff auf Dienstinformationen kann eingeschränkt werden, mithilfe der <xref:System.Security.Permissions.PermissionState> zum Festlegen von Berechtigungen der <xref:System.Security.Permissions.SecurityPermission>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>  
 [Vorgehensweise: Fortsetzen einer Windows-Diensts (Visual Basic)](../../../docs/framework/windows-services/how-to-continue-a-windows-service-visual-basic.md)
