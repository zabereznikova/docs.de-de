---
title: Arbeiten mit dynamischen Objekten (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 78b17a379ea219cc24842322703caaa9d29eeb2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647348"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Arbeiten mit dynamischen Objekten (Visual Basic)
Dynamische Objekte bieten eine weitere Möglichkeit, andere als die `Object` Typ späte Bindung an ein Objekt zur Laufzeit. Ein dynamisches Objekt macht Elemente wie z. B. Eigenschaften und Methoden zur Laufzeit mithilfe von dynamischen Schnittstellen, die in definierten der <xref:System.Dynamic> Namespace. Sie können die Klassen in der <xref:System.Dynamic> Namespace zum Erstellen von Objekten, die mit Datenstrukturen zu arbeiten, der nicht statischen Typ oder Format übereinstimmt. Sie können auch die dynamische Objekte, die in dynamischen Sprachen wie z. B. IronPython und IronRuby definiert sind. Finden Sie Beispiele, die zeigen, wie Sie dynamische Objekte erstellen, oder verwenden Sie ein dynamisches Objekt in einer dynamischen Sprache definiert, [Exemplarische Vorgehensweise: Erstellen und mit dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, oder <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic bindet auf Objekte aus der dynamic Language Runtime und dynamischen Sprachen wie z. B. IronPython und IronRuby mithilfe der <xref:System.Dynamic.IDynamicMetaObjectProvider> Schnittstelle. Beispiele für Klassen, implementieren die `IDynamicMetaObjectProvider` Schnittstelle werden die <xref:System.Dynamic.DynamicObject> und <xref:System.Dynamic.ExpandoObject> Klassen.  
  
 Wenn Sie einen spät gebundenen Aufruf zu einem Objekt ausgeführt wird, die implementiert die `IDynamicMetaObjectProvider` Schnittstelle, bindet die Visual Basic mit dem dynamischen Objekt mit dieser Schnittstelle. Wenn Sie einen spät gebundenen Aufruf zu einem Objekt ausgeführt wird, die nicht implementiert die `IDynamicMetaObjectProvider` -Schnittstelle, oder, wenn der Aufruf der `IDynamicMetaObjectProvider` Schnittstelle ausfällt, Visual Basic-Bindung an das Objekt mithilfe der späte Bindung Funktionen von Visual Basic-Laufzeit.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
