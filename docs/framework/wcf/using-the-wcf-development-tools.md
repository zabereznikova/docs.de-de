---
title: Verwenden der WCF-Entwicklungstools
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 41d2ee2881b79ffb086a931ec6d271d409ac66db
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="using-the-wcf-development-tools"></a>Verwenden der WCF-Entwicklungstools
Dieser Abschnitt beschreibt die Visual Studio-Entwicklungstools, die bei der Entwicklung von Entwicklungswerkzeuge helfen können.  
  
 Sie können die Visual Studio-Vorlagen als Grundlage verwenden, um schnell einen eigenen Dienst zu erstellen, verwenden Sie WCF-Dienst-Auto-Host und WCF-Testclient, Debuggen und Testen des Diensts. Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.  
  
## <a name="the-wcf-developer-tools"></a>Die WCF-Entwicklungstools  
 [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Die vordefinierten Visual Studio Projekt- und Elementvorlagen können in Visual Studio Sie schnell die WCF-Dienste und entsprechende Anwendungen erstellen.  
  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 Der WCF-Dienst-Auto-Host (WcfSvcHost.exe) können Sie zum Starten von Visual Studio-Debugger (F5), um automatisch hosten, und Testen Sie einen Dienst implementiert wurden. Sie können dann testen Sie den Dienst mithilfe der WCF-Testclient (wcfTestClient.exe) oder Ihrem eigenen Client zum Suchen und potenzielle Fehler zu beheben.  
  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 WCF-Testclient (WcfTestClient.exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, und übermitteln Sie, dass Eingaben, die an den Dienst und die zurückgesendete Antwort des Diensts anzeigen. Es bietet eine nahtlose diensttest in Kombination mit WCF-Dienst-Auto-Host.  
  
 [Generieren von Datentypklassen aus XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden. Die in den Daten definierten Klassen werden in Codetypen konvertiert.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Verwenden der Tools ohne Administratorberechtigung  
 Damit kann Benutzer ohne Administratorberechtigung zur Entwicklung von WCF-Diensten, erstellt eine ACL (Access Control List) für den Namespace "http://+:8731/Design_Time_Addresses" während der Installation von Visual Studio. Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden. Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen. Es kann auch Benutzer die WCF-Dienst-Auto-Host (wcfSvcHost.exe) zu verwenden, ohne ihnen Administratorrechte zu gewähren.  
  
 Mit dem Netsh.exe-Tool unter [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern. Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Weitere Informationen zu Netsh.exe, finden Sie unter [wie das Netsh.exe-Tool und Befehlszeilenoptionen](http://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
