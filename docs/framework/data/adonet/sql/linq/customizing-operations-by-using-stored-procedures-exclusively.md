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
# <a name="customizing-operations-by-using-stored-procedures-exclusively"></a><span data-ttu-id="a5608-102">Anpassen von Operationen durch ausschließliche Verwendung von gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="a5608-102">Customizing Operations by Using Stored Procedures Exclusively</span></span>

<span data-ttu-id="a5608-103">Der Zugriff auf Daten nur mit gespeicherten Prozeduren ist ein gängiges Szenario.</span><span class="sxs-lookup"><span data-stu-id="a5608-103">Access to data by using only stored procedures is a common scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5608-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5608-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a5608-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5608-105">Description</span></span>  

 <span data-ttu-id="a5608-106">Sie können das in [Anpassen von Vorgängen angegebene Beispiel mithilfe gespeicherter Prozeduren](customizing-operations-by-using-stored-procedures.md) ändern, indem Sie die erste Abfrage (die die dynamische SQL-Ausführung bewirkt) mit einem Methoden Befehl ersetzen, der eine gespeicherte Prozedur umschließt.</span><span class="sxs-lookup"><span data-stu-id="a5608-106">You can modify the example provided in [Customizing Operations By Using Stored Procedures](customizing-operations-by-using-stored-procedures.md) by replacing even the first query (which causes dynamic SQL execution) with a method call that wraps a stored procedure.</span></span>  
  
 <span data-ttu-id="a5608-107">Gehen Sie wie im folgenden Beispiel von der `CustomersByCity`-Methode aus.</span><span class="sxs-lookup"><span data-stu-id="a5608-107">Assume `CustomersByCity` is the method, as in the following example.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a5608-108">Code</span><span class="sxs-lookup"><span data-stu-id="a5608-108">Code</span></span>  

 [!code-csharp[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/northwind.cs#4)]
 [!code-vb[DLinqOverrideDefaultSproc#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/northwind.vb#4)]  
  
 <span data-ttu-id="a5608-109">Der folgende Code wird ohne jedes dynamische SQL ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a5608-109">The following code executes without any dynamic SQL.</span></span>  
  
 [!code-csharp[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefaultSproc/cs/Program.cs#5)]
 [!code-vb[DLinqOverrideDefaultSproc#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefaultSproc/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="a5608-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5608-110">See also</span></span>

- [<span data-ttu-id="a5608-111">Aufgaben der Entwickler beim Überschreiben von Standardverhalten</span><span class="sxs-lookup"><span data-stu-id="a5608-111">Responsibilities of the Developer In Overriding Default Behavior</span></span>](responsibilities-of-the-developer-in-overriding-default-behavior.md)
