---
title: Gespeicherte Prozeduren
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: b06dc19aa8b767da6a1c6b00bd5b465465db6060
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742835"
---
# <a name="stored-procedures"></a>Gespeicherte Prozeduren
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet Methoden in Ihrem Objektmodell, um gespeicherte Prozeduren in der Datenbank darzustellen. Sie kennzeichnen Methoden als gespeicherte Prozeduren, indem Sie das <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut und bei Bedarf das <xref:System.Data.Linq.Mapping.ParameterAttribute>-Attribut anwenden. Weitere Informationen finden Sie unter [das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Entwickler, die mit Visual Studio würde in der Regel den Object Relational Designer verwenden, gespeicherte Prozeduren zuordnen. Dieser Abschnitt erläutert das Bilden und Aufrufen dieser Methoden in Ihrer Anwendung, wenn Sie den Code selbst schreiben.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Zurückgeben von Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 Beschreibt das Zurückgeben von Datenzeilen und zeigt, wie ein Eingabeparameter verwendet wird.  
  
 [Vorgehensweise: Verwenden von gespeicherten Prozeduren, die Parameter annehmen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 Beschreibt die Verwendung von Eingabe- und Ausgabeparametern.  
  
 [Vorgehensweise: Verwenden von gespeicherten Prozeduren, die mehreren Ergebnisformen zugeordnet sind](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 Beschreibt, wie in der gleichen gespeicherten Prozedur mehrere Formen zurückgegeben werden können.  
  
 [Vorgehensweise: Verwenden von gespeicherten Prozeduren, die sequenziellen Ergebnisformen zugeordnet sind](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 Beschreibt, wie die Unterstützung für mehrere Formen gewährleistet werden kann, wenn die Rückgabesequenz bekannt ist.  
  
 [Anpassen von Operationen durch Verwendung von gespeicherten Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 Beschreibt, wie gespeicherte Prozeduren zur Implementierung von Insert-, Update- und Delete-Operationen verwendet werden.  
  
 [Anpassen von Operationen durch ausschließliche Verwendung von gespeicherten Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 Beschreibt, wie ausschließlich gespeicherte Prozeduren zur Implementierung von Insert-, Update- und Delete-Operationen verwendet werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Programmierhandbuch](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Stellt Informationen zur Erstellung und Nutzung Ihres [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Objektmodells bereit.  
  
 [Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 Umfasst Prozeduren, die veranschaulichen, wie gespeicherte Prozeduren in Visual Basic verwendet werden.  
  
 [Exemplarische Vorgehensweise: Verwenden von gespeicherten Prozeduren nur (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 Umfasst Prozeduren, die veranschaulichen, wie gespeicherte Prozeduren in C# verwendet werden.
