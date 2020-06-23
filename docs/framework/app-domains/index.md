---
title: Programmieren mit Anwendungsdomänen und Assemblys
description: Lernen Sie das Programmieren mit Anwendungsdomänen und Assemblys in .NET kennen. Weitere Informationen finden Sie über Links zu Themen zu Vorgehensweisen und Beispielen zum Erstellen von Anwendungsdomänen und Assemblys.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
- application domains, programming
- programming application domains
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
ms.openlocfilehash: 1c28fe0abeb279a1dbbc6dcf043c1780c72d79df
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903437"
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
