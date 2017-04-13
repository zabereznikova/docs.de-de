---
title: "Marshaling Strings | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "marshaling, samples"
  - "platform invoke, marshaling data"
  - "data marshaling, strings"
  - "data marshaling, samples"
  - "data marshaling, platform invoke"
  - "marshaling. strings"
  - "marshaling, platform invoke"
  - "sample applications [.NET Framework], marshaling strings"
ms.assetid: e21b078b-70fb-4905-be26-c097ab2433ff
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Marshaling Strings
Plattformaufruf kopiert Zeichenfolgenparameter, wobei diese gegebenenfalls aus dem .NET Framework\-Format \(Unicode\) in das nicht verwaltete Format \(ANSI\) konvertiert werden.  Da nicht verwaltete Zeichenfolgen unveränderlich sind, kopiert Plattformaufruf diese bei Rückgabe der Funktion nicht aus dem nicht verwalteten Speicher in den verwalteten Speicher zurück.  
  
 Die folgende Tabelle listet Mashalloptionen für Zeichenfolgen zusammen mit einer Beschreibung ihrer Verwendung und einem Link zum entsprechenden .NET Framework\-Beispiel auf.  
  
|Zeichenfolge|Beschreibung|Beispiel|  
|------------------|------------------|--------------|  
|Durch einen Wert.|Übergibt Zeichenfolgen als In\-Parameter.|[MsgBox](../../../docs/framework/interop/msgbox-sample.md)|  
|Als Ergebnis.|Gibt Zeichenfolgen aus nicht verwaltetem Code zurück.|[Zeichenfolgen](http://msdn.microsoft.com/de-de/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|Durch einen Verweis.|Übergibt Zeichenfolgen als In\/Out\-Parameter unter Verwendung von <xref:System.Text.StringBuilder>.|[Puffer](http://msdn.microsoft.com/de-de/e30d36e8-d7c4-4936-916a-8fdbe4d9ffd5)|  
|In einer Struktur durch einen Wert.|Übergibt Zeichenfolgen als Struktur, die ein In\-Parameter ist.|[Strukturen](http://msdn.microsoft.com/de-de/96a62265-dcf9-4608-bc0a-1f762ab9f48e)|  
|In einer Struktur durch einen Verweis **\(char\*\)**.|Übergibt Zeichenfolgen als Struktur, die ein In\/Out\-Parameter ist.  Die nicht verwaltete Funktion erwartet einen Verweis auf einen Zeichenpuffer, und die Puffergröße ist ein Member der Struktur.|[Zeichenfolgen](http://msdn.microsoft.com/de-de/be9e82a3-dc95-4aaa-9396-61b66e467e02)|  
|In einer Struktur durch einen Verweis **\(char\[\]\)**.|Übergibt Zeichenfolgen als Struktur, die ein In\/Out\-Parameter ist.  Die nicht verwaltete Funktion erwartet einen eingebetteten Zeichenpuffer.|[OSInfo](http://msdn.microsoft.com/de-de/69d89067-507b-41fe-859d-30bf3ff29455)|  
|In einer Struktur durch einen Wert **\(char\*\)**.|Übergibt Zeichenfolgen in einer Klasse. \(Eine Klasse ist ein In\/Out\-Parameter.\)  Die nicht verwaltete Funktion erwartet einen Zeiger auf einen Zeichenpuffer.|[OpenFileDlg](http://msdn.microsoft.com/de-de/b7dea792-cb92-4baf-ac7b-6a24803e6c75)|  
|In einer Struktur durch einen Wert **\(char\[\]\)**.|Übergibt Zeichenfolgen in einer Klasse. \(Eine Klasse ist ein In\/Out\-Parameter.\)  Die nicht verwaltete Funktion erwartet einen eingebetteten Zeichenpuffer.|[OSInfo](http://msdn.microsoft.com/de-de/69d89067-507b-41fe-859d-30bf3ff29455)|  
|Als Array von Zeichenfolgen durch einen Wert.|Erstellt ein Array von Zeichenfolgen, das durch einen Wert übergeben wird.|[Arrays](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
|Als Array von Strukturen, die Zeichenfolgen durch einen Wert enthalten.|Erstellt ein Array von Strukturen, die Zeichenfolgen enthalten. Das Array wird durch einen Wert übergeben.|[Arrays](../../../docs/framework/interop/marshaling-different-types-of-arrays.md)|  
  
## Siehe auch  
 [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)   
 [Platform Invoke Data Types](http://msdn.microsoft.com/de-de/16014d9f-d6bd-481e-83f0-df11377c550f)   
 [Marshaling Classes, Structures, and Unions](../../../docs/framework/interop/marshaling-classes-structures-and-unions.md)   
 [Marshaling Arrays of Types](http://msdn.microsoft.com/de-de/049b1c1b-228f-4445-88ec-91bc7fd4b1e8)   
 [Miscellaneous Marshaling Samples](http://msdn.microsoft.com/de-de/a915c948-54e9-4d0f-a525-95a77fd8ed70)