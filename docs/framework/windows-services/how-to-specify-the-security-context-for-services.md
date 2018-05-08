---
title: 'Gewusst wie: Angeben des Sicherheitskontexts für Dienste'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, security
- security [Visual Studio], contexts
- contexts, Visual Studio security
- security [Visual Studio], service applications
- ServiceProcessInstaller class, security context
- services, security
- ServiceInstaller class, security context
ms.assetid: 02187c7b-dbf2-45f2-96c2-e11010225a22
author: ghogen
manager: douge
ms.openlocfilehash: e3e5ad7dd44dcaf1593ac80bbe6d0a367964e4e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-the-security-context-for-services"></a>Gewusst wie: Angeben des Sicherheitskontexts für Dienste
Standardmäßig werden Dienste in einem anderen Sicherheitskontext als dem des angemeldeten Benutzers ausgeführt. Wird aufgerufen, der Dienst ausgeführt wird, im Rahmen des Standardkontos System `LocalSystem`, die erhalten sie unterschiedliche Zugriffsrechte auf Systemressourcen, als der vom Benutzer. Sie können dieses Verhalten, um ein anderes Benutzerkonto angeben, unter dem der Dienst ausgeführt werden soll, ändern.  
  
 Festlegen des Sicherheitskontexts durch Bearbeiten der <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> Eigenschaft für den Prozess, in dem der Dienst ausgeführt wird. Diese Eigenschaft können Sie den Dienst auf einen der vier Kontotypen festlegen:  
  
-   `User`, die bewirkt, dass des Systems für einen gültigen Benutzernamen und Kennwort aufgefordert werden, wenn der Dienst installiert ist und ausgeführt, im Kontext eines Kontos angegeben, die durch einen einzelnen Benutzer im Netzwerk wird;  
  
-   `LocalService`, der ausgeführt wird, im Kontext eines Kontos, das als nicht berechtigte Benutzer auf dem lokalen Computer fungiert und Remoteservern werden anonyme Anmeldeinformationen alle Remoteserver; übergeben  
  
-   `LocalSystem`, die im Kontext eines Kontos, das umfangreiche lokale Berechtigungen und stellt Anmeldeinformationen des Computers, auf alle RAS-Server ausgeführt wird  
  
-   `NetworkService`, die im Kontext eines Kontos ein, die als nicht berechtigte Benutzer auf dem lokalen Computer fungiert, und stellt die Anmeldeinformationen des Computers mit remote-Server ausgeführt wird.  
  
 Weitere Informationen finden Sie unter der <xref:System.ServiceProcess.ServiceAccount>-Enumeration.  
  
### <a name="to-specify-the-security-context-for-a-service"></a>Um den Sicherheitskontext für einen Dienst anzugeben.  
  
1.  Nachdem Sie den Dienst erstellt haben, fügen Sie die erforderlichen Installationsprogramme hinzu. Weitere Informationen finden Sie unter [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).  
  
2.  Im Designer Zugriff auf die `ProjectInstaller` Klasse, und klicken Sie auf das Dienstinstallationsprogramm-Prozess für den Dienst mit dem Sie arbeiten.  
  
    > [!NOTE]
    >  Für jede dienstanwendung sind mindestens zwei Installationskomponenten in der `ProjectInstaller` Klasse – eine, die die Prozesse für alle Dienste im Projekt und für jeden Dienst, der die Anwendung enthält einen Installer installiert. In diesem Fall sollten Sie auswählen möchten <xref:System.ServiceProcess.ServiceProcessInstaller>.  
  
3.  In der **Eigenschaften** legen die <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> auf den entsprechenden Wert.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [Vorgehensweise: Erstellen von Windows-Diensten](../../../docs/framework/windows-services/how-to-create-windows-services.md)
