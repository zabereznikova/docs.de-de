---
title: Arbeiten mit dynamischen Objekten (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 366b563764baaa39849356a782ecee264b2ae94f
ms.lasthandoff: 03/13/2017

---
# <a name="working-with-dynamic-objects-visual-basic"></a>Arbeiten mit dynamischen Objekten (Visual Basic)
Dynamische Objekte bieten eine weitere Möglichkeit, außer der `Object` Typ späte Bindung an ein Objekt zur Laufzeit. Ein dynamisches Objekt macht Member wie Eigenschaften und Methoden zur Laufzeit mithilfe von dynamischen Schnittstellen, die in definiert sind die <xref:System.Dynamic>Namespace.</xref:System.Dynamic> Sie können die Klassen in der <xref:System.Dynamic>Namespace zum Erstellen von Objekten, die mit Datenstrukturen, die nicht statischen Typ oder Format entsprechen.</xref:System.Dynamic> Sie können auch die dynamische Objekte, die in dynamischen Sprachen wie IronPython und IronRuby definiert sind. Beispiele, die zeigen, wie dynamische Objekte erstellt, oder verwenden Sie ein dynamisches Objekt in einer dynamischen Sprache definiert werden, finden Sie unter [Exemplarische Vorgehensweise: Erstellen und verwenden dynamische Objekte](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, oder <xref:System.Dynamic.ExpandoObject>.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject>  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Mithilfe von Objekten aus der dynamic Language Runtime und dynamische Sprachen wie IronPython und IronRuby gebunden die <xref:System.Dynamic.IDynamicMetaObjectProvider>Schnittstelle.</xref:System.Dynamic.IDynamicMetaObjectProvider> Beispiele für Klassen, implementieren die `IDynamicMetaObjectProvider` Schnittstelle sind die <xref:System.Dynamic.DynamicObject>und <xref:System.Dynamic.ExpandoObject>Klassen.</xref:System.Dynamic.ExpandoObject> </xref:System.Dynamic.DynamicObject>  
  
 Bei ein spät gebundenen Aufruf an ein Objekt implementiert die `IDynamicMetaObjectProvider` -Schnittstelle [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] mithilfe dieser Schnittstelle von dynamischen Objekts gebunden. Erfolgt ein spät gebundenen Aufruf auf ein Objekt, das nicht implementiert die `IDynamicMetaObjectProvider` -Schnittstelle, oder, wenn der Aufruf von der `IDynamicMetaObjectProvider` -Schnittstelle ein Fehler auftritt, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] bindet an das Objekt mithilfe der Funktionen für späte Bindung von der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Common Language Runtime.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Dynamic.DynamicObject></xref:System.Dynamic.DynamicObject>   
 <xref:System.Dynamic.ExpandoObject></xref:System.Dynamic.ExpandoObject>   
 [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)   
 [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
