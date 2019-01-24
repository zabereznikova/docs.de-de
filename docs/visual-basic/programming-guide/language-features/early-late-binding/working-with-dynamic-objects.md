---
title: Arbeiten mit dynamischen Objekten (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 14bd78f2897edc9f2092e062fda16ba5a7d04c37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640861"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Arbeiten mit dynamischen Objekten (Visual Basic)
Dynamische Objekte bieten eine andere Möglichkeit, außer die `Object` Typs, um späte Bindung an ein Objekt zur Laufzeit. Ein dynamisches Objekt macht Member wie etwa Eigenschaften und Methoden zur Laufzeit mithilfe von dynamischen Schnittstellen, die definiert sind die <xref:System.Dynamic> Namespace. Sie können die Klassen in der <xref:System.Dynamic> Namespace zum Erstellen von Objekten, die Datenstrukturen verwenden, die nicht statischen Typ oder Format entsprechen. Sie können auch die dynamische Objekte, die in dynamischen Sprachen wie IronPython und IronRuby definiert sind. Beispiele, die zeigen, wie Sie dynamische Objekte erstellen oder verwenden Sie ein dynamisches Objekt, das in einer dynamischen Sprache definiert, finden Sie unter [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, oder <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic bindet auf Objekte über die dynamic Language Runtime und die dynamische Sprachen wie IronPython und IronRuby mithilfe der <xref:System.Dynamic.IDynamicMetaObjectProvider> Schnittstelle. Beispiele für Klassen, implementieren die `IDynamicMetaObjectProvider` Schnittstelle werden die <xref:System.Dynamic.DynamicObject> und <xref:System.Dynamic.ExpandoObject> Klassen.  
  
 Wenn eine spät gebundene auf ein Objekt aufgerufen wird, die implementiert die `IDynamicMetaObjectProvider` Schnittstelle, Visual Basic-Bindungen in der dynamisches Objekt unter Verwendung dieser Schnittstelle. Wenn eine spät gebundene auf ein Objekt aufgerufen wird, die nicht implementiert die `IDynamicMetaObjectProvider` -Schnittstelle, oder, wenn der Aufruf von der `IDynamicMetaObjectProvider` fehlschlägt, Schnittstelle, die Visual Basic-Bindung an das Objekt mithilfe der Funktionen für die späte Bindung von der Visual Basic-Laufzeit.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
