---
title: "How to: Add Installers to Your Service Application | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Windows Service applications, deploying"
  - "installation components, adding to services"
  - "installers, adding to services"
  - "Windows Service applications, adding installers"
  - "services, adding installers"
  - "ServiceInstaller class, adding installers to services"
  - "ServiceProcessInstaller class, adding installers to services"
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 14
---
# How to: Add Installers to Your Service Application
Im Lieferumfang von Visual Studio sind Installationskomponenten enthalten, mit denen Ressourcen installiert werden können, die Dienstanwendungen zugeordnet sind.  Von Installationskomponenten wird ein einzelner Dienst auf dem System registriert, auf dem er installiert wird. Dem Dienststeuerungs\-Manager wird mitgeteilt, dass der Dienst vorhanden ist.  Wenn mit einer Dienstanwendung gearbeitet wird, können die entsprechenden Installationsprogramme über einen Link im Eigenschaftenfenster dem Projekt hinzugefügt werden.  
  
> [!NOTE]
>  Eigenschaftswerte für einen Dienst werden aus der Dienstklasse in die Installerklasse kopiert.  Wenn Eigenschaftswerte in der Dienstklasse aktualisiert werden, werden sie nicht automatisch im Installationsprogramm aktualisiert.  
  
 Wenn einem Projekt ein Installationsprogramm hinzugefügt wird, wird eine neue Klasse im Projekt erstellt, die den Standardnamen `ProjectInstaller` aufweist. In ihr werden Instanzen der entsprechenden Installationskomponenten erstellt.  Diese Klasse fungiert als zentraler Punkt für alle Installationskomponenten, die für das Projekt benötigt werden.  Wenn z. B. ein zweiter Dienst zur Anwendung hinzugefügt und auf den Link **Installer hinzufügen** geklickt wird, wird keine zweite Installationsprogrammklasse erstellt. Stattdessen werden die für den zweiten Dienst benötigten zusätzlichen Installationskomponenten zur vorhandenen Klasse hinzugefügt.  
  
 Innerhalb der Installationsprogramme wird keine besondere Codierung für die richtige Installation von Diensten benötigt.  Es kann jedoch durchaus notwendig werden, die Inhalte von Installationsprogrammen zu ändern, wenn spezielle Funktionen zum Installationsvorgang hinzugefügt werden müssen.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.  Wählen Sie im Menü **Extras** die Option **Einstellungen importieren und exportieren** aus, um die Einstellungen zu ändern.  Weitere Informationen finden Sie unter [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/de-de/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### So fügen Sie Installationsprogramme zu Dienstanwendungen hinzu  
  
1.  Öffnen Sie im **Projektmappen\-Explorer** die **Entwurfsansicht** für den Dienst, dem eine Installationskomponente hinzugefügt werden soll.  
  
2.  Klicken Sie auf den Hintergrund des Designers, um den Dienst selbst, nicht aber den Inhalt zu markieren.  
  
3.  Klicken Sie mit der rechten Maustaste, wenn der Designer den Fokus hat, und klicken Sie dann auf **Installer hinzufügen**.  
  
     Eine neue Klasse, `ProjectInstaller`, und zwei Installationskomponenten, <xref:System.ServiceProcess.ServiceProcessInstaller> und <xref:System.ServiceProcess.ServiceInstaller>, werden dem Projekt hinzugefügt. Außerdem werden Eigenschaftswerte für den Dienst in die Komponenten kopiert.  
  
4.  Klicken Sie auf die <xref:System.ServiceProcess.ServiceInstaller>\-Komponente. Überprüfen Sie, ob die <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>\-Eigenschaft auf den gleichen Wert festgelegt ist wie die <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>\-Eigenschaft für den Dienst selbst.  
  
5.  Legen Sie fest, wie der Dienst gestartet wird, indem Sie auf die <xref:System.ServiceProcess.ServiceInstaller>\-Komponente klicken und die <xref:System.ServiceProcess.ServiceInstaller.StartType%2A>\-Eigenschaft auf den entsprechenden Wert festlegen.  
  
    |Wert|Ergebnis|  
    |----------|--------------|  
    |<xref:System.ServiceProcess.ServiceStartMode>|Der Dienst muss nach der Installation manuell gestartet werden.  Weitere Informationen finden Sie unter [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).|  
    |<xref:System.ServiceProcess.ServiceStartMode>|Der Dienst wird eigenständig gestartet, wenn der Computer neu gestartet wird.|  
    |<xref:System.ServiceProcess.ServiceStartMode>|Der Dienst kann nicht gestartet werden.|  
  
6.  Legen Sie den Sicherheitskontext fest, in dem ein Dienst ausgeführt wird, indem Sie auf die <xref:System.ServiceProcess.ServiceProcessInstaller>\-Komponente klicken und die entsprechenden Eigenschaftswerte festlegen.  Weitere Informationen finden Sie unter [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).  
  
7.  Überschreiben Sie alle Methoden, für die eine benutzerdefinierte Verarbeitung durchgeführt werden muss.  
  
8.  Führen Sie die Schritte 1 bis 7 für jeden zusätzlichen Dienst in dem Projekt durch.  
  
    > [!NOTE]
    >  Für jeden zusätzlichen Dienst im Projekt muss der `ProjectInstaller`\-Klasse des Projekts eine zusätzliche <xref:System.ServiceProcess.ServiceInstaller>\-Komponente hinzugefügt werden.  Die in Schritt 3 hinzugefügte <xref:System.ServiceProcess.ServiceProcessInstaller>\-Komponente funktioniert mit allen Dienstinstallern im Projekt.  
  
## Siehe auch  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)   
 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)   
 [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md)   
 [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)