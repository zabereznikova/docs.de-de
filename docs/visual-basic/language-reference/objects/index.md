---
title: erzwingen
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic]
ms.assetid: 651c73e4-dca8-402b-9c6b-e3902b3a3f4b
ms.openlocfilehash: 8956d8dd8f46b4235d71802ccc743dfebcb051be
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344156"
---
# <a name="objects-visual-basic"></a>Objekte (Visual Basic)
Dieses Thema stellt Links zu anderen Themen bereit, die die Visual Basic-Laufzeitobjekte dokumentieren und Tabellen der Member und Prozeduren sowie der Eigenschaften und Ereignisse enthalten.  
  
## <a name="visual-basic-run-time-objects"></a>Visual Basic-Laufzeitobjekte  
  
|||  
|---|---|  
|<xref:Microsoft.VisualBasic.Collection>|Stellt eine einfache Möglichkeit dar, eine zusammengehörige Gruppe von Elementen als einzelnes Objekt anzuzeigen.|  
|<xref:Microsoft.VisualBasic.Information.Err%2A>|Enthält Informationen über Laufzeitfehler.|  
|Das `My.Application`-Objekt besteht aus den folgenden Klassen:<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> stellt Member bereit, die in allen Projekten verfügbar sind.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> stellt Member bereit, die in Windows Forms-Anwendungen verfügbar sind.<br /><br /> <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> stellt Member bereit, die in Konsolenanwendungen verfügbar sind.|Stellt Daten bereit, die nur der aktuellen Anwendung oder DLL zugeordnet sind. Mit `My.Application` können keine Informationen auf Systemebene bearbeitet werden.<br /><br /> Einige Member sind nur für Windows Forms- oder Konsolenanwendungen verfügbar.|  
|`My.Application.Info` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Info%2A>)|Stellt Eigenschaften zum Abrufen der Informationen über eine Anwendung bereit, beispielsweise die Versionsnummer, die Beschreibung, die geladenen Assemblys und so weiter.|  
|`My.Application.Log` (<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log%2A>)|Stellt eine Eigenschaft und Methoden zum Schreiben von Ereignis- und Ausnahmeinformationen in die Protokolllistener der Anwendung bereit.|  
|`My.Computer` (<xref:Microsoft.VisualBasic.Devices.Computer>)|Stellt Eigenschaften für die Bearbeitung von Computerkomponenten bereit, z.B. Audio, die Uhr, die Tastatur, das Dateisystem und so weiter.|  
|`My.Computer.Audio` (<xref:Microsoft.VisualBasic.Devices.Audio>)|Stellt Methoden zur Soundwiedergabe bereit.|  
|`My.Computer.Clipboard` (<xref:Microsoft.VisualBasic.Devices.Computer.Clipboard%2A>)|Stellt Methoden zur Bearbeitung der Zwischenablage bereit.|  
|`My.Computer.Clock` (<xref:Microsoft.VisualBasic.Devices.Clock>)|Stellt Eigenschaften für den Zugriff auf die aktuelle lokale Zeit und die koordinierte Weltzeit (entspricht UTC, Greenwich Mean Time) von der Systemuhr bereit.|  
|`My.Computer.FileSystem` (<xref:Microsoft.VisualBasic.FileIO.FileSystem>)|Stellt Eigenschaften und Methoden für die Arbeit mit Laufwerken, Dateien und Verzeichnissen bereit.|  
|`My.Computer.FileSystem.SpecialDirectories` (<xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>)|Stellt Eigenschaften für den Zugriff auf häufig verwiesene Verzeichnisse bereit.|  
|`My.Computer.Info` (<xref:Microsoft.VisualBasic.Devices.ComputerInfo>)|Stellt Eigenschaften zum Abrufen von Informationen über den Arbeitsspeicher des Computer, geladene Assemblys, Name und Betriebssystem bereit.|  
|`My.Computer.Keyboard` (<xref:Microsoft.VisualBasic.Devices.Keyboard>)|Stellt Eigenschaften für den Zugriff auf den aktuellen Zustand der Tastatur bereit, z.B. welche Tasten werden gerade gedrückt? Außerdem bietet es eine Methode, mit der Sie Tastatureingaben an ein aktives Fenster schicken können.|  
|`My.Computer.Mouse` (<xref:Microsoft.VisualBasic.Devices.Mouse>)|Stellt Eigenschaften zum Abrufen von Informationen über das Format und die Konfiguration der Maus bereit, die auf dem lokalen Computer installiert ist.|  
|`My.Computer.Network` (<xref:Microsoft.VisualBasic.Devices.Network>)|Stellt eine Eigenschaft, ein Ereignis und Methoden zur Interaktion mit dem Netzwerk bereit, mit dem der Computer verbunden ist.|  
|`My.Computer.Ports` (<xref:Microsoft.VisualBasic.Devices.Ports>)|Stellt eine Eigenschaft und eine Methode bereit, mit deren Hilfe Sie auf die seriellen Anschlüsse eines Computer zugreifen können.|  
|`My.Computer.Registry` (<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>)|Stellt Eigenschaften und Methoden zur Bearbeitung der Registrierung bereit.|  
|[My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)|Stellt Eigenschaften für den Zugriff auf eine Instanz jedes Windows Form im aktuellen Projekt bereit.|  
|`My.Log` (<xref:Microsoft.VisualBasic.Logging.AspLog>)|Stellt eine Eigenschaft und Methoden zum Schreiben von Ereignis- und Ausnahmeinformationen in die Protokolllistener der Anwendung für Webanwendungen bereit.|  
|[My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)|Ruft das <xref:System.Web.HttpRequest>-Objekt für die angefragte Seite ab. Das `My.Request`-Objekt enthält Informationen zur aktuellen HTTP-Anforderung.<br /><br /> Das `My.Request`-Objekt ist nur für ASP.NET-Anwendungen verfügbar.|  
|[My.Resources-Objekt](../../../visual-basic/language-reference/objects/my-resources-object.md)|Stellt Eigenschaften und Klassen für den Zugriff auf Anwendungsressourcen bereit.|  
|[My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)|Ruft das <xref:System.Web.HttpResponse> zugeordnete <xref:System.Web.UI.Page>-Objekt ab. Mit diesem Objekt können Sie HTTP-Antwortdaten an einen Client senden. Es enthält außerdem Informationen über diese Antwort.<br /><br /> Das `My.Response`-Objekt ist nur für ASP.NET-Anwendungen verfügbar.|  
|[My.Settings-Objekt](../../../visual-basic/language-reference/objects/my-settings-object.md)|Stellt Eigenschaften und Methoden für den Zugriff auf Anwendungseinstellungen bereit.|  
|`My.User` (<xref:Microsoft.VisualBasic.ApplicationServices.User>)|Stellt den Zugriff auf Informationen über den aktuellen Benutzer bereit.|  
|[My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)|Stellt Eigenschaften zum Erstellen einer einzelnen Instanz sowie für den Zugriff auf diese bereit, die für jeden Webdienst gilt, auf die vom aktuellen Projekt verwiesen wird.|  
|<xref:Microsoft.VisualBasic.FileIO.TextFieldParser>|Stellt Methoden und Eigenschaften zur Analyse strukturierter Textdateien bereit.|  
  
## <a name="see-also"></a>Siehe auch

- [Sprachreferenz zu Visual Basic](../../../visual-basic/language-reference/index.md)
- [Visual Basic](../../../visual-basic/index.md)
