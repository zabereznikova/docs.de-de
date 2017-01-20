---
title: "Objects (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "objects [Visual Basic]"
ms.assetid: 651c73e4-dca8-402b-9c6b-e3902b3a3f4b
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Objects (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

In diesem Thema finden Sie Links zu anderen Themen, welche die Visual Basic\-Laufzeitobjekte dokumentieren und Tabellen mit den Prozeduren, Eigenschaften und Ereignissen ihrer Member enthalten.  
  
## Visual Basic\-Laufzeitobjekte  
  
|||  
|-|-|  
|<xref:Microsoft.VisualBasic.Collection>|Stellt eine bequeme Methode zum Anzeigen einer zusammenhängenden Gruppe von Elementen in Form eines einzelnen Objekts bereit.|  
|<xref:Microsoft.VisualBasic.Information.Err%2A>|Enthält Informationen über Laufzeitfehler.|  
|Das `My.Application`\-Objekt umfasst die folgenden Klassen:<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> stellt Member bereit, die in allen Projekten verfügbar sind.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> stellt Member bereit, die in Windows Forms\-Anwendungen verfügbar sind.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> stellt Member bereit, die in Konsolenanwendungen verfügbar sind.|Stellt Daten bereit, die nur der aktuellen Anwendung oder der DLL zugeordnet sind.  Mit `My.Application` können keine Informationen auf Systemebene geändert werden.<br /><br /> Einige Member sind nur für Windows Forms\- oder Konsolenanwendungen verfügbar.|  
|`My.Application.Info` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Info%2A>\)|Stellt Eigenschaften zum Abrufen von Informationen über eine Anwendung bereit, z. B. Versionsnummer, Beschreibung, geladene Assemblys usw.|  
|`My.Application.Log` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>\)|Stellt eine Eigenschaft und Methoden zum Schreiben von Ereignis\- und Ausnahmeinformationen in die Protokollüberwachung der Anwendung bereit.|  
|`My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\)|Stellt Eigenschaften zum Bearbeiten von Computerkomponenten bereit, z. B. Audio, Uhr, Tastatur, Dateisystem usw.|  
|`My.Computer.Audio` \(<xref:Microsoft.VisualBasic.Devices.Audio>\)|Stellt Methoden für die Wiedergabe von Sounds bereit.|  
|`My.Computer.Clipboard` \(<xref:Microsoft.VisualBasic.Devices.Computer.Clipboard%2A>\)|Stellt Methoden zum Bearbeiten der Zwischenablage bereit.|  
|`My.Computer.Clock` \(<xref:Microsoft.VisualBasic.Devices.Clock>\)|Stellt Eigenschaften für den Zugriff auf die aktuelle lokale Uhrzeit und die aktuelle koordinierte Weltzeit \(Universal Coordinated Time, UTC – entspricht Greenwich Mean Time\) der Systemuhr bereit.|  
|`My.Computer.FileSystem` \(<xref:Microsoft.VisualBasic.FileIO.FileSystem>\)|Stellt Eigenschaften und Methoden für das Arbeiten mit Laufwerken, Dateien und Verzeichnissen bereit.|  
|`My.Computer.FileSystem.SpecialDirectories` \(<xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>\)|Stellt Eigenschaften für den Zugriff auf Verzeichnisse bereit, auf die häufig verwiesen wird.|  
|`My.Computer.Info` \(<xref:Microsoft.VisualBasic.Devices.ComputerInfo>\)|Stellt Eigenschaften für das Abrufen von Informationen über den Arbeitsspeicher des Computers, geladene Assemblys, Name und Betriebssystem bereit.|  
|`My.Computer.Keyboard` \(<xref:Microsoft.VisualBasic.Devices.Keyboard>\)|Stellt Eigenschaften für den Zugriff auf den aktuellen Zustand der Tastatur, z. B. Informationen über die derzeit gedrückten Tasten, und eine Methode zum Senden von Tastaturanschlägen an das aktive Fenster bereit.|  
|`My.Computer.Mouse` \(<xref:Microsoft.VisualBasic.Devices.Mouse>\)|Stellt Eigenschaften zum Abrufen von Informationen über das Format und die Konfiguration der auf dem lokalen Computer installierten Maus bereit.|  
|`My.Computer.Network` \(<xref:Microsoft.VisualBasic.Devices.Network>\)|Stellt eine Eigenschaft, ein Ereignis und Methoden zum Interagieren mit dem Netzwerk bereit, mit dem der Computer verbunden ist.|  
|`My.Computer.Ports` \(<xref:Microsoft.VisualBasic.Devices.Ports>\)|Stellt eine Eigenschaft und eine Methode für den Zugriff auf die seriellen Anschlüsse des Computers bereit.|  
|`My.Computer.Registry` \(<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>\)|Stellt Eigenschaften und Methoden zum Bearbeiten der Registrierung bereit.|  
|[My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)|Stellt Eigenschaften für den Zugriff auf eine Instanz von jedem im aktuellen Projekt deklarierten Windows Form bereit.|  
|`My.Log` \(<xref:Microsoft.VisualBasic.Logging.AspLog>\)|Stellt eine Eigenschaft und Methoden zum Schreiben von Ereignis\- und Ausnahmeinformationen in die Protokollüberwachungen für Webanwendungen bereit.|  
|[My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)|Ruft das <xref:System.Web.HttpRequest>\-Objekt für die angeforderte Seite ab.  Das `My.Request`\-Objekt enthält Informationen über die aktuelle HTTP\-Anforderung.<br /><br /> Das `My.Request`\-Objekt ist nur für [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]\-Anwendungen verfügbar.|  
|[My.Resources Object](../../../visual-basic/language-reference/objects/my-resources-object.md)|Stellt Eigenschaften und Klassen für den Zugriff auf die Ressourcen einer Anwendung bereit.|  
|[My.Response Object](../../../visual-basic/language-reference/objects/my-response-object.md)|Ruft das <xref:System.Web.HttpResponse>\-Objekt ab, das dem <xref:System.Web.UI.Page>\-Element zugeordnet ist.  Dieses Objekt ermöglicht das Senden von HTTP\-Antwortdaten an einen Client und enthält Informationen über diese Antwort.<br /><br /> Das `My.Response`\-Objekt ist nur für [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]\-Anwendungen verfügbar.|  
|[My.Settings Object](../../../visual-basic/language-reference/objects/my-settings-object.md)|Stellt Eigenschaften und Methoden für den Zugriff auf die Einstellungen einer Anwendung bereit.|  
|`My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\)|Ermöglicht den Zugriff auf die Informationen über den aktuellen Benutzer.|  
|[My.WebServices Object](../../../visual-basic/language-reference/objects/my-webservices-object.md)|Stellt Eigenschaften bereit, mit denen von jedem Webdienst, auf den das aktuelle Projekt verweist, eine Einzelinstanz erstellt werden bzw. auf diese Einzelinstanz zugegriffen werden kann.|  
|<xref:Microsoft.VisualBasic.FileIO.TextFieldParser>|Stellt Methoden und Eigenschaften zur Analyse strukturierter Textdateien bereit.|  
  
## Siehe auch  
 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)   
 [Visual Basic](../../../visual-basic/index.md)