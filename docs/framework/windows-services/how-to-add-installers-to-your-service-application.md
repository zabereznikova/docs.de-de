---
title: "Gewusst wie: Hinzufügen von Installern zur Dienstanwendung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 0dcb666f317ab285ae0156d2df16947f71665aee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-installers-to-your-service-application"></a>Gewusst wie: Hinzufügen von Installern zur Dienstanwendung
Visual Studio geliefert Installationskomponenten, die Ihre dienstanwendungen zugeordnete Ressourcen installieren können. Installationskomponenten registrieren Sie einen einzelnen Dienst auf dem System, das installiert wird, und lassen Sie den Dienststeuerungs-Manager wissen, dass der Dienst vorhanden ist. Bei der Arbeit mit einer dienstanwendung können Sie einen Link im Fenster Eigenschaften die entsprechenden Installationsprogramme automatisch zu Ihrem Projekt hinzufügen auswählen.  
  
> [!NOTE]
>  Eigenschaftswerte für Ihren Dienst werden aus der Dienstklasse in die Installerklasse kopiert. Wenn Sie die Eigenschaftswerte in die Dienstklasse aktualisieren, werden sie in das Installationsprogramm nicht automatisch aktualisiert.  
  
 Wenn Sie ein Installationsprogramm Ihrem Projekt eine neue Klasse hinzufügen (, die standardmäßig heißt `ProjectInstaller`) wird erstellt, in das Projekt, und klicken Sie auf Instanzen der entsprechenden Installation Komponenten darin erstellt werden. Diese Klasse fungiert als ein zentraler Verwaltungspunkt für alle Installationskomponenten für das Projekt benötigt. Wenn Sie Ihre Anwendung einen zweiten Dienst hinzu, und klicken Sie auf den Link Installer hinzufügen, wird eine zweite Installerklasse z. B. nicht erstellt; Stattdessen wird die vorhandene Klasse der erforderlichen zusätzlichen Installationskomponente für den zweiten Dienst hinzugefügt.  
  
 Sie brauchen keine besondere Codierung innerhalb der Installationsprogramme, stellen die Dienste ordnungsgemäß zu installieren. Allerdings müssen Sie gelegentlich den Inhalt der Installationsprogramme zu ändern, wenn Sie spezielle Funktionen während des Installationsvorgangs hinzufügen müssen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-installers-to-your-service-application"></a>Die dienstanwendung Installationsprogramme hinzu  
  
1.  In **Projektmappen-Explorer**, Zugriff **Entwurf** Ansicht für den Dienst für die Sie eine Komponente hinzufügen möchten.  
  
2.  Klicken Sie auf dem Hintergrund des Designers, um den Dienst ausgewählt haben, selbst statt einen seiner Inhalte.  
  
3.  Mit dem Designer den Fokus hat, mit der rechten Maustaste, und klicken Sie dann auf **Installer hinzufügen**.  
  
     Eine neue Klasse `ProjectInstaller`, und zwei Installationskomponenten <xref:System.ServiceProcess.ServiceProcessInstaller> und <xref:System.ServiceProcess.ServiceInstaller>, hinzukommen zum Projekt und Eigenschaftswerte für der Dienst für die Komponenten kopiert werden.  
  
4.  Klicken Sie auf die <xref:System.ServiceProcess.ServiceInstaller> Komponente und überprüfen Sie, ob der Wert des der <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> Eigenschaftensatz wird auf den gleichen Wert wie die <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> Eigenschaft für den Dienst selbst.  
  
5.  Um zu bestimmen, wie der Dienst gestartet wird, klicken Sie auf die <xref:System.ServiceProcess.ServiceInstaller> Komponente, und legen die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> Eigenschaft auf den entsprechenden Wert.  
  
    |Wert|Ergebnis|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|Der Dienst muss nach der Installation manuell gestartet werden. Weitere Informationen finden Sie unter [Vorgehensweise: Starten von Diensten](../../../docs/framework/windows-services/how-to-start-services.md).|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|Der Dienst kann selbst gestartet, sobald der Computer neu gestartet wurde.|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|Der Dienst kann nicht gestartet werden.|  
  
6.  Um den Sicherheitskontext fest, in dem der Dienst ausgeführt wird, klicken Sie auf die <xref:System.ServiceProcess.ServiceProcessInstaller> Komponente, und legen Sie die entsprechenden Eigenschaftswerte. Weitere Informationen finden Sie unter [Vorgehensweise: Angeben des Sicherheitskontexts für Dienste](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).  
  
7.  Überschreiben Sie alle Methoden, die für die benutzerdefinierte Verarbeitung durchgeführt werden müssen.  
  
8.  Führen Sie die Schritte 1 bis 7 für jeden Dienst in Ihrem Projekt ein.  
  
    > [!NOTE]
    >  Für jeden Dienst in Ihrem Projekt, müssen Sie ein zusätzliches hinzufügen <xref:System.ServiceProcess.ServiceInstaller> -Komponente auf des Projekts `ProjectInstaller` Klasse. Die <xref:System.ServiceProcess.ServiceProcessInstaller> Komponente, die in Schritt 3 hinzugefügten funktioniert mit allen einzelnen Dienstinstallationsprogramm im Projekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [Vorgehensweise: Installieren und Deinstallieren von Diensten](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [Vorgehensweise: Starten von Diensten](../../../docs/framework/windows-services/how-to-start-services.md)  
 [Vorgehensweise: Angeben des Sicherheitskontexts für Dienste](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
