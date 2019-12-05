---
title: Verwenden der WCF-Entwicklungstools
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 8253a9136b2310deeb7c6d162a9f190c13ba02da
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837726"
---
# <a name="using-the-wcf-development-tools"></a>Verwenden der WCF-Entwicklungstools
In diesem Abschnitt werden die Visual Studio-Entwicklungs Tools beschrieben, die Ihnen bei der Entwicklung von WCFService helfen können.  
  
 Sie können die Visual Studio-Vorlagen als Grundlage verwenden, um schnell einen eigenen Dienst zu erstellen, und dann den automatischen WCF-Dienst Host und den WCF-Test Client zum Debuggen und Testen des Diensts verwenden. Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.  
 
 > [!NOTE]
 > Ab Visual Studio 2017 werden die WCF-Entwicklungs Tools nicht standardmäßig installiert. Um diese Features zu verwenden, müssen Sie sicherstellen, dass die Windows Communication Foundation Komponente im Visual Studio-Installer ausgewählt ist.
  
## <a name="the-wcf-developer-tools"></a>Die WCF-Entwicklungstools  
 [WCF Visual Studio-Vorlagen](wcf-vs-templates.md)  
  
 Sie können die vordefinierten Visual Studio-Projekt-und-Element Vorlagen in Visual Studio verwenden, um schnell WCF-Dienste und umgebende Anwendungen zu erstellen.  
  
 [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)  
  
 Mit dem automatischen WCF-Dienst Host (WcfSvcHost. exe) können Sie den Visual Studio-Debugger (F5) starten, um automatisch einen von Ihnen implementierten Dienst zu hosten und zu testen. Anschließend können Sie den Dienst mit dem WCF-Test Client (WcfTestClient. exe) oder Ihrem eigenen Client testen, um potenzielle Fehler zu finden und zu beheben.  
  
 [WCF-Testclient (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)  
  
 Der WCF-Test Client (WcfTestClient. exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, die Eingabe an den Dienst senden und die Antwort anzeigen können, die der Dienst zurücksendet. Diese Funktion bietet eine nahtlose Dienst Testfunktion, wenn Sie mit dem automatischen WCF-Dienst Host kombiniert wird.  
  
 [Generieren von Datentypklassen aus XML](generating-data-type-classes-from-xml.md)  
  
 XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden. Die in den Daten definierten Klassen werden in Codetypen konvertiert.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Verwenden der Tools ohne Administratorberechtigung  
 Um Benutzern ohne Administratorrechte die Entwicklung von WCF-Diensten zu ermöglichen, wird während der Installation von Visual Studio eine ACL (Access Control Liste) für den Namespace "http://+:8731/Design_Time_Addresses" erstellt. Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden. Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen. Außerdem können Benutzer den automatischen WCF-Dienst-Host (WcfSvcHost. exe) verwenden, ohne Ihnen Administratorrechte zu erteilen.  
  
 Sie können den Zugriff mithilfe des Tools "Netsh. exe" in Windows Vista unter dem Konto mit erhöhten Rechten ändern. Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Weitere Informationen zu "Netsh. exe" finden [Sie unter Verwenden des Tools "Netsh. exe" und Befehls Zeilenschalter](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).  
  
## <a name="see-also"></a>Siehe auch

- [WCF Visual Studio-Vorlagen](wcf-vs-templates.md)
- [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [WCF-Testclient (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
