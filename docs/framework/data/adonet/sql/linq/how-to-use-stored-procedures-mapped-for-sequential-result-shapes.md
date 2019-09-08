---
title: 'Vorgehensweise: Verwenden von gespeicherten Prozeduren, die sequenziellen Ergebnisformen zugeordnet sind'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: bae10e823a274304f21292cf55947a4d4eaccc10
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781459"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a>Vorgehensweise: Verwenden von gespeicherten Prozeduren, die sequenziellen Ergebnisformen zugeordnet sind
Diese Art von gespeicherten Prozeduren kann mehr als eine Ergebnisform erstellen. Sie wissen jedoch, in welcher Reihenfolge die Ergebnisse zurückgegeben werden. Stellen Sie dieses Szenario dem Szenario gegenüber, bei dem Sie die Rückgabereihenfolge nicht kennen. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie gespeicherte Prozeduren, die](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)mehreren Ergebnis Formen zugeordnet sind.  
  
## <a name="example"></a>Beispiel  
 Es folgt das T-SQL einer gespeicherten Prozedur, die mehrere Ergebnisformen sequenziell zurückgibt:  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a>Beispiel  
 Um die gespeicherte Prozedur auszuführen, wird in etwa der folgende Code verwendet.  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- [Gespeicherte Prozeduren](stored-procedures.md)
