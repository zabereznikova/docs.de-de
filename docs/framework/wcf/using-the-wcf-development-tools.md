---
title: Verwenden der WCF-Entwicklungstools
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: bfe71c8f4ee515e1895f27166bcb5931806dabea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-wcf-development-tools"></a>Verwenden der WCF-Entwicklungstools
In diesem Abschnitt wird beschrieben, die Visual Studio-Entwicklungstools, die Ihnen, bei der Entwicklung helfen können Ihrer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]Dienst.  
  
 Sie können die Visual Studio-Vorlagen als Grundlage verwenden, schnell einen eigenen Dienst zu erstellen, dann verwenden Sie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst-Auto-Host und [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Client testen, Debuggen und Testen des Diensts. Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.  
  
## <a name="the-wcf-developer-tools"></a>Die WCF-Entwicklungstools  
 [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 Sie können die vordefinierten Visual Studio Projekt- und Elementvorlagen in Visual Studio verwenden, beim schnellen Erstellen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienste und entsprechende Anwendungen.  
  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 Die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienst-Auto-Host (WcfSvcHost.exe) können Sie zum Starten von Visual Studio-Debugger (F5), um zu hosten und automatisch einen implementierten Dienst zu testen. Anschließend können Sie den Dienst mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient (wcfTestClient.exe) oder Ihrem eigenen Client testen, um potenzielle Fehler zu identifizieren und zu beheben.  
  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 Der [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Testclient (WcfTestClient.exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, die Eingabe an den Dienst senden und die zurückgesendete Antwort des Diensts anzeigen können. Zusammen mit dem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host ermöglicht er einen problemlosen Diensttest.  
  
 [Generieren von Datentypklassen aus XML](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden. Die in den Daten definierten Klassen werden in Codetypen konvertiert.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Verwenden der Tools ohne Administratorberechtigung  
 So aktivieren Sie die Benutzer ohne Administratorberechtigung entwickeln [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Dienste eine ACL (Access Control List) wird erstellt, für den Namespace "http://+:8731/Design_Time_Addresses" während der Installation von Visual Studio. Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden. Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen. Darüber hinaus haben Benutzer die Möglichkeit, den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst-Auto-Host (wcfSvcHost.exe) zu verwenden, ohne dass ihnen Administratorberechtigungen zugewiesen werden müssen.  
  
 Mit dem Netsh.exe-Tool unter [!INCLUDE[wv](../../../includes/wv-md.md)] unter dem erweiterten Administratorkonto können Sie die Zugriffsberechtigung ändern. Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Weitere Informationen zu Netsh.exe, finden Sie unter [wie das Netsh.exe-Tool und Befehlszeilenoptionen](http://go.microsoft.com/fwlink/?LinkId=97877).  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Visual Studio-Vorlagen](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [WCF-Diensthost (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [WCF-Testclient (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
