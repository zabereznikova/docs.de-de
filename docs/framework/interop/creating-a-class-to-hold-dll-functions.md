---
title: "Creating a Class to Hold DLL Functions | Microsoft Docs"
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
  - "COM interop, DLL functions"
  - "unmanaged functions"
  - "COM interop, platform invoke"
  - "interoperation with unmanaged code, DLL functions"
  - "interoperation with unmanaged code, platform invoke"
  - "platform invoke, creating class for functions"
  - "DLL functions"
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Creating a Class to Hold DLL Functions
Wenn Sie eine häufig verwendete DLL\-Funktion mit einer verwalteten Klasse umschließen, können Sie die Plattformfunktionen auf effektive Weise kapseln.  Dies ist zwar nicht in jedem Fall erforderlich, doch können Sie mithilfe von Klassenwrappern die DLL\-Funktionen mit weniger Aufwand und geringerer Fehleranfälligkeit definieren.  Wenn Sie in Visual Basic oder C\# programmieren, müssen Sie die DLL\-Funktionen in einer Klasse oder in einem Visual Basic\-Modul deklarieren.  
  
 Innerhalb einer Klasse definieren Sie eine statische Methode für jede DLL\-Funktion, die Sie aufrufen möchten.  Die Definition kann zusätzliche Informationen enthalten, z. B. den Zeichensatz oder die Aufrufkonvention, die zur Übergabe von Methodenargumenten verwendet wird. Wenn Sie diese Informationen weglassen, werden die standardmäßigen Einstellungen verwendet.  Eine vollständige Liste aller Deklarationsoptionen und ihrer Standardeinstellungen finden Sie unter [Erstellen von Prototypen in verwaltetem Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).  
  
 Sobald eine Funktion umschlossen ist, können Sie dafür in gleicher Weise Methoden aufrufen wie für eine beliebige statische Funktion.  Durch einen Plattformaufruf werden automatisch die zugrunde liegenden exportierten Funktionen behandelt.  
  
 Achten Sie beim Entwurf einer verwalteten Klasse für Plattformaufruf auf die Beziehungen zwischen Klassen und DLL\-Funktionen.  Sie haben unter anderem folgende Möglichkeiten:  
  
-   DLL\-Funktionen in einer vorhandenen Klasse deklarieren.  
  
-   Eine einzelne Klasse für jede DLL\-Funktion erstellen. Auf diese Weise bleiben die Funktionen isoliert und sind leicht aufzufinden.  
  
-   Eine Klasse für einen Satz verwandter DLL\-Funktionen erstellen, um logische Gruppen zu bilden und den Verwaltungsaufwand zu verringern.  
  
 Sie können die Klasse und ihre Methoden beliebig benennen.  Beispiele für das Erstellen von .NET\-basierten Deklarationen, die mit Plattformaufruf verwendet werden, finden Sie unter [Marshallen von Daten mit Plattformaufruf](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## Siehe auch  
 [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)   
 [Identifying Functions in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md)   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Calling a DLL Function](../../../docs/framework/interop/calling-a-dll-function.md)