---
title: Verwenden der WCF-Entwicklungstools
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 3eb349fd795b2067d4d75ff138fd9b5922110bd3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44037876"
---
# <a name="using-the-wcf-development-tools"></a>Verwenden der WCF-Entwicklungstools
Dieser Abschnitt beschreibt die Visual Studio-Entwicklungstools, die Sie bei der Entwicklung von Entwicklungswerkzeuge unterstützen können.  
  
 Sie können Visual Studio-Vorlagen als Grundlage verwenden, um einen eigenen Dienst schnell zu erstellen und dann die WCF-Dienst-Auto-Host und WCF-Testclient zum Debuggen und Testen des Diensts verwenden. Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.  
  
## <a name="the-wcf-developer-tools"></a>Die WCF-Entwicklungstools  
 [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Sie können die vordefinierten Visual Studio Projekt- und Elementvorlagen in Visual Studio verwenden, um WCF-Dienste und entsprechende Anwendungen schnell erstellen.  
  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 Der WCF-Dienst-Auto-Host (WcfSvcHost.exe) können Sie zum Starten von Visual Studio-Debugger (F5), um automatisch zu hosten und Testen einen Dienst, den Sie implementiert haben. Anschließend können Sie den Dienst mit den WCF-Testclient (wcfTestClient.exe) oder Ihrem eigenen Client zum Suchen und beheben potenzielle Fehler testen.  
  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 WCF-Testclient (WcfTestClient.exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, übermitteln, die Eingabe an den Dienst und die zurückgesendete Anzeigen der Antwort des Diensts. Es bietet eine nahtlose diensttest in Kombination mit WCF-Dienst-Auto-Host.  
  
 [Generieren von Datentypklassen aus XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden. Die in den Daten definierten Klassen werden in Codetypen konvertiert.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Verwenden der Tools ohne Administratorberechtigung  
 Um Benutzer ohne Administratorrechte zum Entwickeln von WCF-Dienste zu aktivieren, wird eine ACL (Access Control List) erstellt, für den Namespace "http://+:8731/Design_Time_Addresses" während der Installation von Visual Studio. Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden. Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen. Sie können auch Benutzer die WCF-Dienst-Auto-Host (wcfSvcHost.exe) zu verwenden, ohne ihnen Administratorrechte zu gewähren.  
  
 Mit dem Netsh.exe-Tool unter [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern. Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Weitere Informationen zu Netsh.exe, finden Sie unter [wie mit dem Netsh.exe-Tool und die Befehlszeilenoptionen](https://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
