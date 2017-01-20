---
title: "Interoperabilit&#228;t (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C#-Sprache, Interoperabilität"
  - "COM-Interop"
  - "Interoperabilität"
  - "Plattformaufruf, Zugreifen auf APIs mit C#"
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Interoperabilit&#228;t (C#-Programmierhandbuch)
Interoperabilität bietet Ihnen die Möglichkeit, Ihre vorhandenen Investitionen in nicht verwalteten Code zu erhalten und weiterhin davon zu profitieren.  Code, der unter der Kontrolle der Common Language Runtime \(CLR\) ausgeführt wird, wird als *verwalteter Code* bezeichnet. Im Gegensatz dazu wird Code, der außerhalb der CLR ausgeführt wird, als *nicht verwalteter Code* bezeichnet.  Beispiele für nicht verwalteten Code sind COM, COM\+, C\+\+\-Komponenten, ActiveX\-Komponenten und die Microsoft Win32\-API.  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] ermöglicht durch Plattformaufrufdienste, den <xref:System.Runtime.InteropServices>\-Namespace, die C\+\+\-Interoperabilität und die COM\-Interoperabilität \(COM\-Interop\) die Interoperabilität mit nicht verwaltetem Code.  
  
## In diesem Abschnitt  
 [Überblick über die Interoperabilität](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 Beschreibt Methoden für die Interoperabilität zwischen verwaltetem C\#\-Code und nicht verwalteten Code.  
  
 [Gewusst wie: Zugreifen auf Office\-Interop\-Objekte mithilfe von Visual C\#\-Funktionen](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 Beschreibt Funktionen, die in Visual C\# 2010 eingeführt werden, um die Office\-Programmierung zu erleichtern.  
  
 [Gewusst wie: Indizierte Eigenschaften bei der COM\-Interop\-Programmierung](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 Beschreibt, wie indizierte Eigenschaften verwendet werden, um auf COM\-Eigenschaften zuzugreifen, die über Parameter verfügen.  
  
 [Gewusst wie: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 Beschreibt die Verwendung der Plattformaufrufdienste zum Wiedergeben einer WAV\-Datei im Betriebssystem Windows.  
  
 [Exemplarische Vorgehensweise: Office\-Programmierung](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 Zeigt, wie eine Excel\-Arbeitsmappe und ein Word\-Dokument erstellt, das einen Link zur Arbeitsmappe enthält.  
  
 [COM\-Beispielklasse](../../../csharp/programming-guide/interop/example-com-class.md)  
 Veranschaulicht, wie eine C\#\-Klasse als COM\-Objekt verfügbar gemacht wird.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Exemplarische Vorgehensweise: Office\-Programmierung](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)