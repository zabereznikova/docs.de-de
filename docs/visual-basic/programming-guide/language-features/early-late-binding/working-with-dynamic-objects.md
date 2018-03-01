---
title: "Arbeiten mit dynamischen Objekten (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- dynamic objects [Visual Basic]
ms.assetid: bdee2a00-07ff-46f9-86dd-fdac9b99cc97
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: da70c1e4c7398ad46d48c85b62ab884675bd1a73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="working-with-dynamic-objects-visual-basic"></a>Arbeiten mit dynamischen Objekten (Visual Basic)
Dynamische Objekte bieten eine weitere Möglichkeit, andere als die `Object` Typ späte Bindung an ein Objekt zur Laufzeit. Ein dynamisches Objekt macht Elemente wie z. B. Eigenschaften und Methoden zur Laufzeit mithilfe von dynamischen Schnittstellen, die in definierten der <xref:System.Dynamic> Namespace. Sie können die Klassen in der <xref:System.Dynamic> Namespace zum Erstellen von Objekten, die mit Datenstrukturen zu arbeiten, der nicht statischen Typ oder Format übereinstimmt. Sie können auch die dynamische Objekte, die in dynamischen Sprachen wie z. B. IronPython und IronRuby definiert sind. Finden Sie Beispiele, die zeigen, wie Sie dynamische Objekte erstellen, oder verwenden Sie ein dynamisches Objekt in einer dynamischen Sprache definiert, [Exemplarische Vorgehensweise: Erstellen und mit dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md), <xref:System.Dynamic.DynamicObject>, oder <xref:System.Dynamic.ExpandoObject>.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]bindet auf Objekte aus der dynamic Language Runtime und dynamischen Sprachen wie z. B. IronPython und IronRuby mithilfe der <xref:System.Dynamic.IDynamicMetaObjectProvider> Schnittstelle. Beispiele für Klassen, implementieren die `IDynamicMetaObjectProvider` Schnittstelle werden die <xref:System.Dynamic.DynamicObject> und <xref:System.Dynamic.ExpandoObject> Klassen.  
  
 Wenn Sie einen spät gebundenen Aufruf zu einem Objekt ausgeführt wird, die implementiert die `IDynamicMetaObjectProvider` Schnittstelle [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] mithilfe dieser Schnittstelle von dynamischen Objekts gebunden. Wenn Sie einen spät gebundenen Aufruf zu einem Objekt ausgeführt wird, die nicht implementiert die `IDynamicMetaObjectProvider` -Schnittstelle, oder, wenn der Aufruf von der `IDynamicMetaObjectProvider` -Schnittstelle ein Fehler auftritt, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] bindet das Objekt mithilfe der Funktionen spätes Binden, der die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Common Language Runtime.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Dynamic.DynamicObject>  
 <xref:System.Dynamic.ExpandoObject>  
 [Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten](../../../../csharp/programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)  
 [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
