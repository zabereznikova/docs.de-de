---
title: 'Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung'
description: Hier erfahren Sie, wie Sie Installationsprogramme zu Ihrer Dienstanwendung hinzufügen. Visual Studio liefert Installationskomponenten, mit denen Ihren Dienst-Apps zugeordnete Ressourcen installiert werden können.
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
ms.openlocfilehash: 451f0db21e80dfc3dc40052179ac4ec60c2aabdc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96270666"
---
# <a name="how-to-add-installers-to-your-service-application"></a>Vorgehensweise: Hinzufügen von Installern zur Dienstanwendung

Visual Studio liefert Installationskomponenten, mit denen Ihren Dienstanwendungen zugeordnete Ressourcen installiert werden können. Installationskomponenten registrieren einen einzelnen Dienst auf dem System, auf dem dieser installiert wird, und informieren den Dienststeuerungs-Manager über das Vorhandensein des Diensts. Bei der Arbeit mit einer Dienstanwendung können Sie im Fenster „Eigenschaften“ einen Link auswählen, damit die entsprechenden Installer für Ihr Projekt automatisch hinzugefügt werden.  
  
> [!NOTE]
> Eigenschaftswerte für Ihren Dienst werden aus der Dienstklasse in die Klasse des Installers kopiert. Wenn Sie die Eigenschaftswerte in der Dienstklasse aktualisieren, werden sie nicht automatisch im Installer aktualisiert.  
  
 Wenn Sie einen Installer zu Ihrem Projekt hinzufügen, wird in dem Projekt eine neue Klasse erstellt (sie trägt standardmäßig den Namen `ProjectInstaller`), und in dieser Klasse werden Instanzen der entsprechenden Installationskomponenten erstellt. Diese Klasse fungiert als Mittelpunkt für sämtliche Installationspunkte, die für Ihr Projekt erforderlich sind. Wenn Sie beispielsweise einen zweiten Dienst zu Ihrer App hinzufügen und auf den Link „Installer hinzufügen“ klicken, wird keine zweite Installerklasse erstellt. Stattdessen wird die erforderliche zusätzliche Installationskomponente für den zweiten Dienst zur vorhandenen Klasse hinzugefügt.  
  
 Für eine ordnungsgemäße Installation Ihrer Dienste ist innerhalb der Installer keine besondere Codierung erforderlich. Sie müssen jedoch möglicherweise gelegentlich die Inhalte der Installer ändern, wenn Sie besondere Funktionen zum Installer hinzufügen müssen.  
  
> [!NOTE]
> Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-installers-to-your-service-application"></a>Vorgehensweise beim Hinzufügen von Installern zu Ihrer Dienstanwendung  
  
1. Greifen Sie im **Projektmappen-Explorer** bei dem Dienst, für den Sie eine Installationskomponente hinzufügen möchten, auf die Ansicht **Entwurf** zu.  
  
2. Klicken Sie auf den Hintergrund des Designers, um den Dienst selbst auszuwählen, nicht Elemente seines Inhalts.  
  
3. Führen Sie einen Rechtsklick aus, während der Designer den Fokus hat, und klicken Sie anschließend auf **Installer hinzufügen**.  
  
     Eine neue Klasse, `ProjectInstaller`, und zwei Installationskomponenten, <xref:System.ServiceProcess.ServiceProcessInstaller> und <xref:System.ServiceProcess.ServiceInstaller>, werden zu Ihrem Projekt hinzugefügt, und Eigenschaftswerte für den Dienst werden in die Komponenten kopiert.  
  
4. Klicken Sie auf die Komponente <xref:System.ServiceProcess.ServiceInstaller>, und überprüfen Sie, ob der Wert der Eigenschaft <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> auf den gleichen Wert festgelegt ist wie der Wert der Eigenschaft <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> für den Dienst selbst.  
  
5. Klicken Sie auf die Komponente <xref:System.ServiceProcess.ServiceInstaller>, und legen Sie die Eigenschaft <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> auf den entsprechenden Wert fest, um zu bestimmen, wie Ihr Dienst gestartet wird.  
  
    |Wert|Ergebnis|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|Der Dienst muss nach der Installation manuell gestartet werden. Weitere Informationen finden Sie unter [Vorgehensweise: Starten von Diensten](how-to-start-services.md).|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|Der Dienst startet selbst, sobald der Computer neu gestartet wird.|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|Der Dienst kann nicht gestartet werden.|  
  
6. Klicken Sie auf die Komponente <xref:System.ServiceProcess.ServiceProcessInstaller>, und legen Sie die entsprechenden Eigenschaftswerte fest, um den Sicherheitskontext zu bestimmen, in dem Ihr Dienst ausgeführt wird. Weitere Informationen finden Sie unter [Vorgehensweise: Angeben des Sicherheitskontexts für Dienste](how-to-specify-the-security-context-for-services.md).  
  
7. Setzen Sie alle Methoden außer Kraft, für die eine benutzerdefinierte Verarbeitung durchgeführt werden muss.  
  
8. Führen Sie für jeden weiteren Dienst in Ihrem Projekt die Schritte 1 bis 7 durch.  
  
    > [!NOTE]
    > Sie müssen für jeden weiteren Dienst in Ihrem Projekt eine zusätzliche <xref:System.ServiceProcess.ServiceInstaller>-Komponente für die Klasse `ProjectInstaller` des Projekts hinzufügen. Die in Schritt 3 hinzugefügte Komponente <xref:System.ServiceProcess.ServiceProcessInstaller> kann mit allen Dienstinstallern im Projekt ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Windows-Dienstanwendungen](introduction-to-windows-service-applications.md)
- [How to: Installieren und Deinstallieren von Diensten](how-to-install-and-uninstall-services.md)
- [How to: Starten von Diensten](how-to-start-services.md)
- [How to: Angeben des Sicherheitskontexts für Dienste](how-to-specify-the-security-context-for-services.md)
