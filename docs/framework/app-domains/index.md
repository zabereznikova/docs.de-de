---
title: Programmieren mit Anwendungsdomänen und Assemblys
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
ms.openlocfilehash: 3f66eacaf30f8001cdbf3a486e5ce1c878712e2f
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644271"
---
# <a name="programming-with-application-domains-and-assemblies"></a>Programmieren mit Anwendungsdomänen und Assemblys

Hosts wie z.B. Microsoft Internet Explorer, ASP.NET und Windows-Shell laden die Common Language Runtime in einen Prozess, erstellen eine [Anwendungsdomäne](application-domains.md) in diesem Prozess und laden dann Benutzercode in diese Anwendungsdomäne und führen ihn aus, wenn eine .NET Framework-Anwendung ausgeführt wird. In den meisten Fällen müssen Sie sich nicht darum kümmern, Anwendungsdomänen zu erstellen und Assemblys hinein zu laden, da der Laufzeithost diese Aufgaben ausführt.  
  
Wenn Sie jedoch eine Anwendung erstellen, die die Common Language Runtime hostet, Tools oder Code erstellen, den Sie programmgesteuert entladen möchten, oder austauschbare Komponenten erstellen, die spontan entladen und neu geladen werden können, erstellen Sie Ihre eigenen Anwendungsdomänen. Auch wenn Sie keinen Laufzeithost erstellen, können Sie diesem Abschnitt wichtige Informationen entnehmen zum Arbeiten mit Anwendungsdomänen und Assemblys, die in diese Anwendungsdomänen geladen werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

[Gewusst-wie-Themen zu Anwendungsdomänen und Assemblys](application-domains-and-assemblies-how-to-topics.md)  
Enthält Links zu allen Gewusst-wie-Themen in der Begriffsdokumentation zum Programmieren mit Anwendungsdomänen und Assemblys.  
  
[Verwenden von Anwendungsdomänen](use.md)  
Stellt Beispiele zum Erstellen, Konfigurieren und Verwenden von Anwendungsdomänen bereit.  
  
[Programmieren mit Assemblys](../../standard/assembly/index.md)  
Beschreibt das Erstellen, Signieren und Festlegen von Attributen für Assemblys.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

[Ausgeben von dynamischen Methoden und Assemblys](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
Beschreibt das Erstellen dynamischer Assemblys.  
  
[Assemblys in .NET](../../standard/assembly/index.md)  
Bietet eine konzeptionelle Übersicht über Assemblys.  
  
[Anwendungsdomänen](application-domains.md)  
Bietet eine konzeptionelle Übersicht über Anwendungsdomänen.  
  
[Übersicht über Reflektion](../reflection-and-codedom/reflection.md)  
Beschreibt, wie die **Reflektion**-Klasse verwendet wird, um Informationen zu einer Assembly abzurufen.
