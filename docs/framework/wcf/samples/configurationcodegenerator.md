---
title: ConfigurationCodeGenerator
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3913aae8-165f-4014-9262-7fe426f90cb2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06885494f944a916671125a57132bd3ae706a79d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="configurationcodegenerator"></a>ConfigurationCodeGenerator
Der ConfigurationCodeGenerator ist ein Tool, mit dem Sie Ihre Implementierungen von benutzerdefinierten Kanälen für das Konfigurationssystem verfügbar machen können. Auf diese Weise können Benutzer den benutzerdefinierten Kanal wie bei vom System bereitgestellten Bindungen (wie `NetTcpBinding`) oder benutzerdefinierten Bindungen mit dem `TcpTransportBindingElement` mithilfe einer .config-Datei konfigurieren.  
  
 Wenn Sie einen benutzerdefinierten Kanal schreiben und ihn mit einem neuen `BindingElement` oder einer neuen `Binding` für das Programmiermodell verfügbar machen, müssen Sie eine Reihe von Klassen erstellen, damit das `BindingElement` bzw. die `Binding` mit einer .config-Datei konfiguriert werden kann. Mit dem Tool ConfigurationCodeGenerator können Sie diese Klassen generieren und Ihren Kunden die Arbeit erleichtern.  
  
### <a name="to-build-the-tool"></a>So erstellen Sie das Tool  
  
1.  Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Beim Erstellen der Projektmappe wird eine Datei generiert: ConfigurationCodeGenerator.exe. Die Datei "samplerun.cmd" hat eine Beispielbefehlszeile, das veranschaulicht, verwenden Sie dieses Tool zum Generieren der Klassen für die [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) Beispiel.  
  
### <a name="to-run-the-tool"></a>So führen Sie das Tool aus  
  
1.  Wenn Sie sowohl einen benutzerdefinierten `BindingElement`-Typ als auch einen benutzerdefinierten `Binding`-Typ haben, geben Sie an der Eingabeaufforderung Folgendes ein:  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereTheseTypesAreDefined  
    ```  
  
     Wenn Sie nur einen benutzerdefinierten `BindingElement`-Typ haben, geben Sie Folgendes ein:  
  
    ```  
    ConfigurationCodeGenerator.exe /be:YourCustomBindingElementTypeName /dll: TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     Wenn Sie nur einen benutzerdefinierten `Binding`-Typ haben, geben Sie Folgendes ein:  
  
    ```  
    ConfigurationCodeGenerator.exe /sb:YourCustomStdBindingTypeName /dll:TheAssemblyWhereThisTypeIsDefined  
    ```  
  
     Der Befehl generiert drei .cs-Dateien für das `BindingElement` (wenn sie die Option "/be:" angegeben haben), fünf .cs-Dateien für die normale `Binding` (wenn Sie die Option "/sb:" angegeben haben), und eine .xml-Datei.  
  
    1.  Bei Verwendung der Option "/be" implementiert eine der .cs-Dateien den `BindingElementExtensionSection` für Ihr Bindungselement. Dieser Code macht Ihr `BindingElement` für das Konfigurationssystem verfügbar, sodass Ihr Bindungselement auch von anderen benutzerdefinierten Bindungen verwendet werden kann. Die anderen Dateien enthalten Klassen, die Standardwerte und Konstanten darstellen. Die Dateien enthalten `//TODO`-Kommentare, um Sie daran zu erinnern, die Standardwerte zu aktualisieren.  
  
    2.  Wenn Sie die Option "/sb" angegeben haben, implementieren zwei der .cs-Dateien ein `StandardBindingElement` bzw. ein `StandardBindingCollectionElement`, das Ihre Standardbindung für das Konfigurationssystem verfügbar macht. Die anderen Dateien enthalten Klassen, die Standardwerte und Konstanten darstellen. Die Dateien enthalten `//TODO`-Kommentare, um Sie daran zu erinnern, die Standardwerte zu aktualisieren.  
  
         Wenn Sie die /sb angegeben: option enthält die Datei CodeToAddTo\<*YourStdBinding*> .cs Code, den Sie manuell in die Klasse einfügen müssen, die Ihre standardbindung implementiert aufweist.  
  
     Die Datei "SampleConfig.xml" enthält den Konfigurationscode, den Sie der Konfigurationsdatei hinzufügen müssen, die die oben in Schritt 1 oder 2 definierten Handler registriert.  
  
## <a name="see-also"></a>Siehe auch
