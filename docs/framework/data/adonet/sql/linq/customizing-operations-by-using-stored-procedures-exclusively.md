---
title: Anpassen von Operationen durch ausschließliche Verwendung von gespeicherten Prozeduren
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 441e8ef3-998c-4d12-8825-ce66a178f90f
ms.openlocfilehash: 78db5cf448a19056d7265ab84d97d055748c3faa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164323"
---
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a>Anpassen von Operationen durch ausschließliche Verwendung von gespeicherten Prozeduren

Der Zugriff auf Daten nur mit gespeicherten Prozeduren ist ein gängiges Szenario.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  

 Sie können das in [Anpassen von Vorgängen angegebene Beispiel mithilfe gespeicherter Prozeduren](customizing-operations-by-using-stored-procedures.md) ändern, indem Sie die erste Abfrage (die die dynamische SQL-Ausführung bewirkt) mit einem Methoden Befehl ersetzen, der eine gespeicherte Prozedur umschließt.  
  
 Gehen Sie wie im folgenden Beispiel von der `CustomersByCity`-Methode aus.  
  
### <a name="code"></a>Code  

 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 Der folgende Code wird ohne jedes dynamische SQL ausgeführt.  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Aufgaben der Entwickler beim Überschreiben von Standardverhalten](responsibilities-of-the-developer-in-overriding-default-behavior.md)
