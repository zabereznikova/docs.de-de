---
title: Arbeiten mit dynamischen Objekten
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 45f8b5c327d40f93b59c2115c75b3b7d385f5a8d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91057922"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Arbeiten mit dynamischen Objekten (Visual Basic)

Dynamische Objekte bieten andere Möglichkeiten, als den- `Object` Typ, um zur Laufzeit eine spätere Bindung an ein Objekt zu erhalten. Ein dynamisches Objekt macht Member wie Eigenschaften und Methoden zur Laufzeit mithilfe dynamischer Schnittstellen verfügbar, die im- <xref:System.Dynamic> Namespace definiert sind. Sie können die Klassen im- <xref:System.Dynamic> Namespace verwenden, um-Objekte zu erstellen, die mit Datenstrukturen arbeiten, die keinem statischen Typ oder Format entsprechen. Sie können auch die dynamischen Objekte verwenden, die in dynamischen Sprachen wie IronPython und IronRuby definiert sind. Beispiele, die zeigen, wie dynamische Objekte erstellt oder ein dynamisches Objekt verwendet wird, das in einer dynamischen Sprache definiert ist, finden Sie unter Exemplarische Vorgehensweise [: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject> oder <xref:System.Dynamic.ExpandoObject> .  
  
 Visual Basic mithilfe der-Schnittstelle an Objekte aus der Dynamic Language Runtime und dynamische Sprachen wie IronPython und IronRuby gebunden <xref:System.Dynamic.IDynamicMetaObjectProvider> . Beispiele für Klassen, die die `IDynamicMetaObjectProvider` -Schnittstelle implementieren, sind die <xref:System.Dynamic.DynamicObject> <xref:System.Dynamic.ExpandoObject> Klassen und.  
  
 Wenn an einem Objekt, das die-Schnittstelle implementiert, ein spät gebundener-Rückruf erfolgt `IDynamicMetaObjectProvider` , Visual Basic mithilfe dieser Schnittstelle an das dynamische Objekt gebunden. Wenn an einem Objekt, das die-Schnittstelle nicht implementiert, ein spät gebundener aufrufsvorgang erfolgt `IDynamicMetaObjectProvider` oder der- `IDynamicMetaObjectProvider` Schnittstellen Versuch fehlschlägt, wird Visual Basic an das-Objekt gebunden, indem die Funktionen der Visual Basic-Laufzeit verwendet werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Frühes und spätes Binden](index.md)
