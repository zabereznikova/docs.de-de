---
title: "Overview of the Visual Basic Application Model | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Application object, Visual Basic application model"
  - "Visual Basic application model"
ms.assetid: 17538984-84fe-43c9-82c8-724c9529fe8b
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# Overview of the Visual Basic Application Model
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enthält ein klar definiertes Modell für die Steuerung des Verhaltens von Windows Forms\-Anwendungen: das [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Anwendungsmodell.  Dieses Modell umfasst Ereignisse zum Starten und Schließen einer Anwendung sowie Ereignisse zum Abfangen nicht verarbeiteter Ausnahmen.  Darüber hinaus wird die Entwicklung von Einzelinstanzanwendungen unterstützt.  Da das Anwendungsmodell erweiterbar ist, können die überschreibbaren Methoden des Modells bei Bedarf angepasst werden.  
  
## Verwendung des Anwendungsmodells  
 Anwendungen müssen i. d. R. beim Starten und Beenden der Anwendung bestimmte Aufgaben ausführen.  Beim Starten der Anwendung kann beispielsweise ein Begrüßungsbildschirm angezeigt, eine Datenbankverbindung hergestellt oder ein zuvor gespeicherter Zustand geladen werden.  Beim Schließen der Anwendung kann z. B. die Datenbankverbindung geschlossen und der aktuelle Zustand gespeichert werden.  Darüber hinaus kann die Anwendung speziellen Code ausführen, wenn sie unerwartet beendet wird, z. B. bei einer nicht verarbeiteten Ausnahme.  
  
 Mit dem [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Anwendungsmodell können problemlos *Einzelinstanzanwendungen* erstellt werden.  Im Gegensatz zu einer regulären Anwendung kann bei einer Einzelinstanzanwendung nur jeweils eine Instanz der Anwendung ausgeführt werden.  Beim Versuch, eine weitere Instanz einer Einzelinstanzanwendung zu erstellen, wird die ursprüngliche Instanz hierüber mithilfe des `StartupNextInstance`\-Ereignisses benachrichtigt.  Die Benachrichtigung umfasst auch Informationen über die Befehlszeilenargumente der nachfolgenden Instanz.  Anschließend wird die nachfolgende Instanz der Anwendung ohne weitere Initialisierung geschlossen.  
  
 Eine Einzelinstanzanwendung überprüft beim Start, ob sie die erste oder eine nachfolgende Instanz der Anwendung ist. Abhängig vom Ergebnis der Überprüfung geschieht Folgendes:  
  
-   Wenn es sich um die erste Instanz handelt, wird ein normaler Startvorgang ausgeführt.  
  
-   Bei jedem nachfolgenden Versuch, die Anwendung zu starten, während die erste Instanz ausgeführt wird, verhält sich die Anwendung grundlegend anders.  Die nachfolgende Instanz benachrichtigt die erste Instanz über die verwendeten Befehlszeilenargumente und wird dann sofort beendet.  Die erste Instanz verarbeitet das `StartupNextInstance`\-Ereignis, um die für die nachfolgende Instanz verwendeten Befehlszeilenargumente zu ermitteln, und wird dann weiter normal ausgeführt.  
  
     In diesem Diagramm wird dargestellt, wie eine nachfolgende Instanz die erste Instanz benachrichtigt.  
  
     ![Bild zur Einzelinstanzanwendung](../../../visual-basic/developing-apps/development-with-my/media/singleinstance.gif "SingleInstance")  
  
 Durch Verarbeitung des `StartupNextInstance`\-Ereignisses können Sie das Verhalten einer Einzelinstanzanwendung festlegen.  So wird z. B. Microsoft Outlook im Allgemeinen als Einzelinstanzanwendung ausgeführt. Wenn bereits eine Instanz von Outlook ausgeführt wird und Sie versuchen, eine weitere Instanz von Outlook zu starten, wechselt der Fokus zur ursprünglichen Instanz, und es wird keine weitere Instanz geöffnet.  
  
## Ereignisse im Anwendungsmodell  
 Folgende Ereignisse sind im Anwendungsmodell verfügbar:  
  
-   **Start der Anwendung**.  Beim Starten einer Anwendung löst diese das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>\-Ereignis aus.  Durch Verarbeiten dieses Ereignisses können Sie Code hinzufügen, der die Anwendung vor dem Laden des Hauptformulars initialisiert.  Das `Startup`\-Ereignis bietet bei Bedarf auch die Möglichkeit, die Anwendung in dieser Phase des Startvorgangs zu beenden.  
  
     Sie können die Anwendung so konfigurieren, dass während des Startvorgangs ein Begrüßungsbildschirm angezeigt wird.  In der Standardeinstellung wird der Begrüßungsbildschirm bei Verwendung der Befehlszeilenargumente `/nosplash` bzw. `-nosplash` unterdrückt.  
  
-   **Einzelinstanzanwendungen**.  Beim Starten einer nachfolgenden Instanz einer Einzelinstanzanwendung wird das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>\-Ereignis ausgelöst.  Das Ereignis übergibt die Befehlszeilenargumente, die für die nachfolgende Instanz verwendet wurden.  
  
-   **Nicht verarbeitete Ausnahmen**.  Wenn in der Anwendung eine unbehandelte Ausnahme auftritt, löst sie das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>\-Ereignis aus.  Der Handler für dieses Ereignis kann die Ausnahme überprüfen und bestimmen, ob Ausführung fortgesetzt wird.  
  
     In einigen Fällen wird das `UnhandledException`\-Ereignis nicht ausgelöst.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>.  
  
-   **Änderungen an der Verfügbarkeit des Netzwerks**.  Wenn sich die Netzwerkverfügbarkeit für den Computer ändert, löst die Anwendung das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>\-Ereignis aus.  
  
     In einigen Fällen wird das `NetworkAvailabilityChanged`\-Ereignis nicht ausgelöst.  Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>.  
  
-   **Beenden der Anwendung**.  Beim Beenden einer Anwendung löst diese das <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>\-Ereignis aus.  Im zugehörigen Ereignishandler können Sie sicherstellen, dass alle erforderlichen Vorgänge abgeschlossen werden, beispielsweise Schließen und Speichern.  Sie können eine Anwendung so konfigurieren, dass diese beim Schließen des Hauptformulars oder erst nach dem Schließen aller Formulare geschlossen wird.  
  
## Verfügbarkeit  
 Das [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Anwendungsmodell ist standardmäßig für Windows Forms\-Projekte verfügbar.  Wenn Sie eine Anwendung für die Verwendung eines anderen Startobjekts konfigurieren oder den Anwendungscode mit einem benutzerdefinierten Aufruf von `Sub Main` starten, muss dieses Objekt oder diese Klasse ggf. eine Implementierung der <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>\-Klasse bereitstellen, um das Anwendungsmodell verwenden zu können.  Weitere Informationen über das Ändern des Startobjekts finden Sie unter [Seite "Anwendung", Projekt\-Designer \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic).  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.StartupNextInstance>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.NetworkAvailabilityChanged>   
 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>   
 [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)