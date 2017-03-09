---
title: "Working with Dynamic Objects (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "dynamic objects [Visual Basic]"
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Working with Dynamic Objects (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Dynamische Objekte bieten neben dem `Object`\-Typ eine andere Möglichkeit für die späte Bindung an ein Objekt zur Laufzeit.  Ein dynamisches Objekt macht zur Laufzeit Member, z. B. Eigenschaften und Methoden, mithilfe dynamischer Schnittstellen verfügbar, die im <xref:System.Dynamic>\-Namespace definiert sind.  Sie können die Klassen im <xref:System.Dynamic>\-Namespace verwenden, um Objekte zu erstellen, die Datenstrukturen unterstützen, die keinem statischen Typ oder Format entsprechen.  Sie können auch die dynamischen Objekte verwenden, die in dynamischen Sprachen, z. B. IronPython und IronRuby, definiert sind.  Beispiele, die veranschaulichen, wie dynamische Objekte erstellt werden oder wie ein dynamisches in einer dynamischen Sprache definiertes Objekt verwendet wird, finden Sie unter [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject> oder <xref:System.Dynamic.ExpandoObject>.  
  
 In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] werden Bindungen an Objekte aus der dynamischen Sprachlaufzeit und dynamischen Sprachen wie IronPython und IronRuby mithilfe der <xref:System.Dynamic.IDynamicMetaObjectProvider>\-Schnittstelle erstellt.  Beispiele für Klassen, die die Schnittstelle `IDynamicMetaObjectProvider` implementieren, sind <xref:System.Dynamic.DynamicObject> und <xref:System.Dynamic.ExpandoObject>.  
  
 Bei einem spät gebundenen Aufruf eines Objekts, das die `IDynamicMetaObjectProvider`\-Schnittstelle implementiert, erstellt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] unter Verwendung dieser Schnittstelle eine Bindung an das dynamische Objekt.  Bei einem spät gebundenen Aufruf eines Objekts, das die `IDynamicMetaObjectProvider`\-Schnittstelle nicht implementiert, oder bei einem fehlgeschlagenen Aufruf der `IDynamicMetaObjectProvider`\-Schnittstelle erstellt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] die Bindung an das Objekt unter Verwendung der Funktionen für späte Bindung der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Laufzeit.  
  
## Siehe auch  
 <xref:System.Dynamic.DynamicObject>   
 <xref:System.Dynamic.ExpandoObject>   
 [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)   
 [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)