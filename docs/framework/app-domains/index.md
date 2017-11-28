---
title: "Programmieren mit Anwendungsdomänen und Assemblys"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6dcf8e4c9bf2401309b1d80d2306bd619b96460d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="programming-with-application-domains-and-assemblies"></a>Programmieren mit Anwendungsdomänen und Assemblys
Hosts wie z.B. Microsoft Internet Explorer, ASP.NET und Windows-Shell laden die Common Language Runtime in einen Prozess, erstellen eine [Anwendungsdomäne](../../../docs/framework/app-domains/application-domains.md) in diesem Prozess und laden dann Benutzercode in diese Anwendungsdomäne und führen ihn aus, wenn eine .NET Framework-Anwendung ausgeführt wird. In den meisten Fällen müssen Sie sich nicht darum kümmern, Anwendungsdomänen zu erstellen und Assemblys hinein zu laden, da der Laufzeithost diese Aufgaben ausführt.  
  
 Wenn Sie jedoch eine Anwendung erstellen, die die Common Language Runtime hostet, Tools oder Code erstellen, den Sie programmgesteuert entladen möchten, oder austauschbare Komponenten erstellen, die spontan entladen und neu geladen werden können, erstellen Sie Ihre eigenen Anwendungsdomänen. Auch wenn Sie keinen Laufzeithost erstellen, können Sie diesem Abschnitt wichtige Informationen entnehmen zum Arbeiten mit Anwendungsdomänen und Assemblys, die in diese Anwendungsdomänen geladen werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Gewusst-wie-Themen zu Anwendungsdomänen und Assemblys](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 Enthält Links zu allen Gewusst-wie-Themen in der Begriffsdokumentation zum Programmieren mit Anwendungsdomänen und Assemblys.  
  
 [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)  
 Stellt Beispiele zum Erstellen, Konfigurieren und Verwenden von Anwendungsdomänen bereit.  
  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Beschreibt das Erstellen, Signieren und Festlegen von Attributen für Assemblys.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Ausgeben von dynamischen Methoden und Assemblys](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Beschreibt das Erstellen dynamischer Assemblys.  
  
 [Assemblys in der Common Language Runtime (CLR)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Bietet eine konzeptionelle Übersicht über Assemblys.  
  
 [Anwendungsdomänen](../../../docs/framework/app-domains/application-domains.md)  
 Bietet eine konzeptionelle Übersicht über Anwendungsdomänen.  
  
 [Übersicht über Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.
