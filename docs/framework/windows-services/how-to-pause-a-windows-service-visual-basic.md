---
title: 'Vorgehensweise: Anhalten von Windows-Diensten (Visual Basic)'
description: Hier erfahren Sie, wie Sie die ServiceController-Komponente verwenden, um einen Windows-Dienst (z. B. den IIS-Verwaltungsdienst) auf einem lokalen Computer mit Visual Basic anzuhalten.
ms.date: 03/30/2017
dev_langs:
- vb
f1_keywords:
- ServiceController.Pause
helpviewer_keywords:
- Windows Service applications, pausing
- pausing Windows Service applications
ms.assetid: eddb9409-942b-46b6-a2ce-fbd4c65f2790
author: ghogen
ms.openlocfilehash: 628cc2e896f7f8a289e52674b721c4aef605854c
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925565"
---
# <a name="how-to-pause-a-windows-service-visual-basic"></a>Vorgehensweise: Anhalten von Windows-Diensten (Visual Basic)
In diesem Beispiel wird die <xref:System.ServiceProcess.ServiceController>-Komponente verwendet, um den IIS-Verwaltungsdienst auf dem lokalen Computer anzuhalten.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbRadconService#11](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#11)]  
[!code-vb[VbRadconService#12](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#12)]  
  
 Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar. Er befindet sich in der Codeausschnittauswahl unter **Windows-Betriebssystem > Windows-Dienste**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Einen Projektverweis auf „System.serviceprocess.dll“.  
  
- Zugriff auf die Member des <xref:System.ServiceProcess>-Namespace Fügen Sie eine `Imports`-Anweisung hinzu, wenn Sie Membernamen in Ihrem Code nicht vollqualifizieren. Weitere Informationen finden Sie unter [Imports-Anweisung (.NET-Namespace und -typ)](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die Standardeinstellung für die <xref:System.ServiceProcess.ServiceController.MachineName%2A>-Eigenschaft der <xref:System.ServiceProcess.ServiceController>-Klasse ist der lokale Computer. Ändern Sie zum Verweisen auf die Windows-Dienste auf einem anderen Computer die <xref:System.ServiceProcess.ServiceController.MachineName%2A>-Eigenschaft in den Namen des entsprechenden Computers.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Der Dienst kann nicht angehalten werden. (<xref:System.InvalidOperationException>)  
  
- Beim Zugreifen auf eine System-API ist ein Fehler aufgetreten. (<xref:System.ComponentModel.Win32Exception>)  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Die Steuerung von Diensten auf dem Computer kann mithilfe von <xref:System.ServiceProcess.ServiceControllerPermissionAccess> eingeschränkt werden, um Berechtigungen in <xref:System.ServiceProcess.ServiceControllerPermission> festzulegen.  
  
 Der Zugriff auf Dienstinformationen kann mithilfe von <xref:System.Security.Permissions.PermissionState> eingeschränkt werden, um Berechtigungen in <xref:System.Security.Permissions.SecurityPermission> festzulegen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceProcess.ServiceController>
- <xref:System.ServiceProcess.ServiceControllerStatus>
- <xref:System.ServiceProcess.ServiceController.WaitForStatus%2A>
- [How to: Fortsetzen eines Windows-Diensts (Visual Basic)](how-to-continue-a-windows-service-visual-basic.md)
