---
title: "Generieren und Kompilieren von dynamischem Quellcode | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Code Document Object Model (CodeDOM)"
  - "CodeDOM"
  - "Sprachunabhängige Quellcodemodellierung"
  - "Sprachen, Unterstützung mehrerer Sprachen durch CodeDOM"
  - "Mehrere durch CodeDOM unterstützte Sprachen"
  - "Quellcode in mehreren Sprachen"
  - "System.CodeDom-Namespace"
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Generieren und Kompilieren von dynamischem Quellcode
.NET Framework enthält einen Mechanismus mit der Bezeichnung Code\-Dokumentobjektmodell \(Code Document Object Model, CodeDOM\), mit dem die Entwickler von Programmen, die Quellcode ausgeben, die Ausgabe von Quellcode in mehreren Programmiersprachen zur Laufzeit generieren können. Die Grundlage hierfür ist ein Modell, das den zu rendernden Code darstellt.  
  
 Bei der Darstellung von Quellcode werden CodeDOM\-Elemente miteinander verknüpft, sodass sich eine Datenstruktur ergibt, die die Struktur von Quellcode nachbildet. Diese Struktur wird als CodeDOM\-Diagramm bezeichnet.  
  
 Der `System.CodeDom`\-Namespace definiert Typen, die die logische Struktur von Quellcode unabhängig von einer bestimmten Programmiersprache darstellen können.  Der `System.CodeDom.Compiler`\-Namespace definiert Typen zum Generieren von Quellcode aus CodeDOM\-Diagrammen und zum Verwalten der Quellcodekompilierung in unterstützten Sprachen.  Compilerhersteller und Entwickler können die Gruppe der unterstützten Sprachen erweitern.  
  
 Die sprachunabhängige Quellcodemodellierung eignet sich insbesondere für Programme, die Quellcode für ein Programmiermodell in mehreren Sprachen generieren, oder für den Fall, dass die Zielsprache nicht feststeht.  Beispielsweise können Entwickler CodeDOM als Schnittstelle für die Sprachabstraktion verwenden, um Quellcode in der richtigen Programmiersprache zu erstellen, sofern CodeDOM von der Sprache unterstützt wird.  
  
 .NET Framework enthält Code\-Generatoren und Codecompiler für [C\#](frlrfMicrosoftCSharpCSharpCodeProviderClassTopic), [JScript](frlrfMicrosoftJScriptJScriptCodeProviderClassTopic) und [Visual Basic](frlrfMicrosoftVisualBasicVBCodeProviderClassTopic).  
  
## In diesem Abschnitt  
 [Verwenden von CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md)  
 Beschreibt häufige Verwendungsweisen und veranschaulicht das Erstellen eines einfachen Objektdiagramms mithilfe von CodeDOM.  
  
 [Generieren von Quellcode und Kompilieren eines Programms aus einem CodeDOM\-Diagramm](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)  
 Beschreibt das Generieren von Quellcode und das Kompilieren von generiertem Code mit einem externen Compiler anhand von Klassen, die im `System.CodeDom.Compiler`\-Namespace definiert sind.  
  
 [Gewusst wie: Erstellen einer XML\-Dokumentationsdatei mit CodeDOM](../../../docs/framework/reflection-and-codedom/how-to-create-an-xml-documentation-file-using-codedom.md)  
 Beschreibt die Verwendung von CodeDOM, um Code mit XML\-Dokumentationskommentaren zu generieren und den generierten Code zu kompilieren, sodass die XML\-Dokumentationsausgabe erstellt wird.  
  
 [Gewusst wie: Erstellen einer Klasse mit CodeDOM](../../../docs/framework/reflection-and-codedom/how-to-create-a-class-using-codedom.md)  
 Beschreibt die Verwendung von CodeDOM, um eine Klasse mit Feldern, Eigenschaften, einer Methode, einem Konstruktor und einem Einstiegspunkt zu generieren.  
  
## Referenz  
 <xref:System.CodeDom>  
 Definiert Elemente, die Codeelemente in von der Common Language Runtime unterstützten Programmiersprachen darstellen.  
  
 <xref:System.CodeDom.Compiler>  
 Definiert Schnittstellen zum Generieren und Kompilieren von Code zur Laufzeit.  
  
## Verwandte Abschnitte  
 [CodeDOM Quick Reference](http://msdn.microsoft.com/de-de/c77b8bfd-0a32-4e36-b59a-4f687f32c524)  
 Vereinfacht Entwicklern das Auffinden von CodeDOM\-Elementen, die Quellcodeelemente darstellen.