---
title: "Programmieren mit Anwendungsdom&#228;nen und Assemblys | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Anwendungsdomänen, Programmieren"
  - "Assemblys [.NET Framework], Programmieren"
  - "Programmierungsanwendungsdomänen"
  - "Programmieren von Assemblys"
ms.assetid: 96d3b8e3-bef8-4da0-9a81-9841e23a94e9
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Programmieren mit Anwendungsdom&#228;nen und Assemblys
Hosts, wie Microsoft Internet Explorer, ASP.NET und Windows Shell, laden die Common Language Runtime in einen Prozess und erstellen darin eine [Anwendungsdomäne](../../../docs/framework/app-domains/application-domains.md). Anschließend wird in diese Anwendungsdomäne beim Ausführen einer .NET\-Anwendung Benutzercode geladen und dort ausgeführt.  In den meisten Fällen erübrigt es sich, dass Sie selbst Anwendungsdomänen erstellen und Assemblys in diese Domänen laden, da der Host diese Aufgaben übernimmt.  
  
 In folgenden Fällen müssen Sie dies jedoch selbst tun: wenn Sie eine Anwendung erstellen, in der die Common Language Runtime gehostet werden soll, wenn Sie Tools oder Code erstellen, die Sie programmgesteuert entladen möchten, oder wenn Sie Komponenten erstellen, die dynamisch entladen und erneut geladen werden können.  Auch wenn Sie keinen Laufzeithost erstellen möchten, finden Sie in diesem Abschnitt wichtige Informationen über die Arbeit mit Anwendungsdomänen und das Laden von Assemblys in diese Domänen.  
  
## In diesem Abschnitt  
 [Gewusst\-wie\-Themen zu Anwendungsdomänen und Assemblys](../../../docs/framework/app-domains/application-domains-and-assemblies-how-to-topics.md)  
 Enthält Links zu allen Gewusst\-wie\-Themen in der Begriffsdokumentation zum Programmieren mit Anwendungsdomänen und Assemblys.  
  
 [Verwenden von Anwendungsdomänen](../../../docs/framework/app-domains/use.md)  
 Enthält Beispiele für das Erstellen, Konfigurieren und Verwenden von Anwendungsdomänen.  
  
 [Programmieren mit Assemblys](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 Beschreibt das Erstellen, Signieren und Festlegen von Attributen für Assemblys.  
  
## Verwandte Abschnitte  
 [Ausgeben von dynamischen Methoden und Assemblys](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Beschreibt das Erstellen dynamischer Assemblys.  
  
 [Assemblys in der Common Language Runtime \(CLR\)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Bietet eine konzeptionelle Übersicht über Assemblys.  
  
 [Anwendungsdomänen](../../../docs/framework/app-domains/application-domains.md)  
 Bietet eine konzeptionelle Übersicht über Anwendungsdomänen.  
  
 [Übersicht über Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Beschreibt das Verwenden der **Reflection**\-Klasse, um Informationen zu einer Assembly zu erhalten.