---
title: Verwenden der WCF-Entwicklungstools
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183078"
---
# <a name="using-the-wcf-development-tools"></a>Verwenden der WCF-Entwicklungstools
In diesem Abschnitt werden die Visual Studio-Entwicklungstools beschrieben, die Sie bei der Entwicklung Ihres WCFservice unterstützen können.  
  
 Sie können die Visual Studio-Vorlagen als Grundlage verwenden, um schnell Ihren eigenen Dienst zu erstellen, und dann WCF Service Auto Host und WCF Test Client verwenden, um Ihren Dienst zu debuggen und zu testen. Diese Tools ermöglichen Ihnen die Durchführung eines schnellen und problemlosen Test- und Debugzyklus, ohne sich bereits in einem frühen Stadium auf ein Host-Modell festlegen zu müssen.  

 > [!NOTE]
 > Ab Visual Studio 2017 werden die WCF-Entwicklungstools standardmäßig nicht installiert. Um diese Features verwenden zu können, müssen Sie sicherstellen, dass die Windows Communication Foundation-Komponente im Visual Studio-Installationsprogramm ausgewählt ist.
  
## <a name="the-wcf-developer-tools"></a>Die WCF-Entwicklungstools  
 [WCF Visual Studio-Vorlagen](wcf-vs-templates.md)  
  
 Sie können die vordefinierten Visual Studio-Projekt- und Elementvorlagen in Visual Studio verwenden, um WCF-Dienste und umgebende Anwendungen schnell zu erstellen.  
  
 [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)  
  
 Mit dem WCF Service Auto Host (WcfSvcHost.exe) können Sie den Visual Studio-Debugger (F5) starten, um einen von Ihnen implementierten Dienst automatisch zu hosten und zu testen. Anschließend können Sie den Dienst mit dem WCF-Testclient (wcfTestClient.exe) oder Ihrem eigenen Client testen, um mögliche Fehler zu finden und zu beheben.  
  
 [WCF-Testclient (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)  
  
 WCF Test Client (WcfTestClient.exe) ist ein GUI-Tool, mit dem Sie Parameter beliebiger Typen eingeben, diese Eingabe an den Dienst übermitteln und die Antwort anzeigen können, die der Dienst zurücksendet. In Kombination mit WCF Service Auto Host bietet es eine nahtlose Servicetestumgebung.  
  
 [Generieren von Datentypklassen aus XML](generating-data-type-classes-from-xml.md)  
  
 XML-Daten in der Zwischenablage können in eine Codepage eingefügt werden. Die in den Daten definierten Klassen werden in Codetypen konvertiert.  
  
## <a name="using-the-tools-without-administrator-privilege"></a>Verwenden der Tools ohne Administratorberechtigung  
 Um Benutzern ohne Administratorberechtigung das Entwickeln von WCF-Diensten zu ermöglichen, wirdhttp://+:8731/Design_Time_Addresseswährend der Installation von Visual Studio eine ACL (Access Control List) für den Namespace " erstellt. Die ACL wird auf (UI) festgelegt, wodurch alle interaktiven, am Computer angemeldeten Benutzer eingeschlossen werden. Administratoren können dieser ACL Benutzer hinzufügen, Benutzer aus der ACL entfernen oder zusätzliche Ports öffnen. Mit dieser ACL können WCF-Vorlagen oder WF-Vorlagen Daten in ihrer Standardkonfiguration senden und empfangen. Außerdem können Benutzer den WCF Service Auto Host (wcfSvcHost.exe) verwenden, ohne ihnen Administratorrechte zu gewähren.  
  
 Sie können den Zugriff mit dem Tool Netsh.exe in Windows Vista unter dem erweiterten Administratorkonto ändern. Das folgende Beispiel veranschaulicht die Verwendung des Netsh.exe-Tools:  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Weitere Informationen zu Netsh.exe finden Sie unter [Verwenden des Netsh.exe-Tools und der Befehlszeilenschalter](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF Visual Studio-Vorlagen](wcf-vs-templates.md)
- [WCF-Diensthost (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)
- [WCF-Testclient (WcfTestClient.exe)](wcf-test-client-wcftestclient-exe.md)
