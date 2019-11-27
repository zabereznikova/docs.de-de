---
title: Arbeiten mit dynamischen Objekten
ms.date: 07/20/2015
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
ms.openlocfilehash: 20d007fb48e1db352bab6d8e25d2e60e02554732
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345163"
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Arbeiten mit dynamischen Objekten (Visual Basic)
Dynamische Objekte bieten andere Möglichkeiten, als den `Object`-Typ, um zur Laufzeit eine spätere Bindung an ein Objekt zu erhalten. Ein dynamisches Objekt macht Member, wie z. b. Eigenschaften und Methoden zur Laufzeit, mithilfe dynamischer Schnittstellen verfügbar, die im <xref:System.Dynamic>-Namespace definiert sind. Sie können die Klassen im <xref:System.Dynamic>-Namespace verwenden, um-Objekte zu erstellen, die mit Datenstrukturen arbeiten, die nicht einem statischen Typ oder Format entsprechen. Sie können auch die dynamischen Objekte verwenden, die in dynamischen Sprachen wie IronPython und IronRuby definiert sind. Beispiele, die zeigen, wie dynamische Objekte erstellt oder ein dynamisches Objekt verwendet wird, das in einer dynamischen Sprache definiert ist, finden Sie unter Exemplarische Vorgehensweise [: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>oder <xref:System.Dynamic.ExpandoObject>.  
  
 Visual Basic mithilfe der <xref:System.Dynamic.IDynamicMetaObjectProvider>-Schnittstelle an Objekte aus der Dynamic Language Runtime und dynamische Sprachen wie IronPython und IronRuby gebunden. Beispiele für Klassen, die die `IDynamicMetaObjectProvider`-Schnittstelle implementieren, sind die Klassen <xref:System.Dynamic.DynamicObject> und <xref:System.Dynamic.ExpandoObject>.  
  
 Wenn ein-Objekt, das die `IDynamicMetaObjectProvider`-Schnittstelle implementiert, an ein Objekt gebunden wird, Visual Basic an das dynamische Objekt mithilfe dieser Schnittstelle gebunden. Wenn bei einem Objekt, das die `IDynamicMetaObjectProvider`-Schnittstelle nicht implementiert, ein spät gebundener aufrufbedarf erfolgt oder der `IDynamicMetaObjectProvider` Schnittstellen Aufrufe fehlschlägt, wird Visual Basic an das-Objekt gebunden, indem die Funktionen für die späte Bindung der Visual Basic Laufzeit verwendet werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Dynamic.DynamicObject>
- <xref:System.Dynamic.ExpandoObject>
- [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
