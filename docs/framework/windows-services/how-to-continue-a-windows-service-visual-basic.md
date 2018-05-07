---
title: 'Gewusst wie: Fortsetzen eines Windows-Diensts (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Continue
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: e5d13760-4c83-4b0d-abef-39852677cd7a
author: ghogen
manager: douge
ms.openlocfilehash: 15ef15e0afe43d56db0972a686cd093e22c672dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-continue-a-windows-service-visual-basic"></a>Gewusst wie: Fortsetzen eines Windows-Diensts (Visual Basic)
Dieses Beispiel verwendet die <xref:System.ServiceProcess.ServiceController> Komponente, für die IIS-Verwaltungsdienst auf dem lokalen Computer zu fortfahren.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#13](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#13)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. In der Codeausschnittauswahl befindet sich im **Windows-Betriebssystem > Windows-Dienste**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein Projektverweis zu System.serviceprocess.dll.  
  
-   Zugriff auf die Member des <xref:System.ServiceProcess>-Namespace Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die <xref:System.ServiceProcess.ServiceController.MachineName%2A> Eigenschaft von der <xref:System.ServiceProcess.ServiceController> Klasse ist der lokale Computer standardmäßig. Um Windows-Dienste auf einem anderen Computer verweisen, ändern Sie die <xref:System.ServiceProcess.ServiceController.MachineName%2A> -Eigenschaft auf den Namen des betreffenden Computers.  
  
 Sie können nicht aufgerufen werden der <xref:System.ServiceProcess.ServiceController.Continue%2A> Methode für einen Dienst, bis der Status des Controllers ist <xref:System.ServiceProcess.ServiceControllerStatus.Paused>.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Dienst kann nicht fortgesetzt werden. (<xref:System.InvalidOperationException>)  
  
-   Beim Zugreifen auf eine System-API ist ein Fehler aufgetreten. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Die Steuerung von Diensten auf dem Computer kann eingeschränkt werden, mithilfe der <xref:System.ServiceProcess.ServiceControllerPermissionAccess> Enumeration zum Festlegen von Berechtigungen der <xref:System.ServiceProcess.ServiceControllerPermission> Klasse.  
  
 Zugriff auf Dienstinformationen kann eingeschränkt werden, mithilfe der <xref:System.Security.Permissions.PermissionState> Enumeration zum Festlegen von Berechtigungen der <xref:System.Security.Permissions.SecurityPermission> Klasse.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceProcess.ServiceController>  
 <xref:System.ServiceProcess.ServiceControllerStatus>  
 [Vorgehensweise: Anhalten von Windows-Diensten (Visual Basic)](../../../docs/framework/windows-services/how-to-pause-a-windows-service-visual-basic.md)
