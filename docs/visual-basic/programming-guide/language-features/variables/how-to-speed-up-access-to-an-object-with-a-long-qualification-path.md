---
title: 'Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: b10876c22d2f6dd5832baa0d498db7c4205a3fcb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816290"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="ff2c3-102">Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff2c3-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="ff2c3-103">Wenn Sie häufig ein Objekt, die einen Qualifizierungspfad, der mehrere Methoden und Eigenschaften erforderlich sind zugreifen, können Sie Ihren Code beschleunigen, indem nicht wiederholt den Qualifizierungspfad.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="ff2c3-104">Es gibt zwei Möglichkeiten, die Sie vermeiden können, wiederholen den Qualifizierungspfad.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="ff2c3-105">Sie können das Objekt einer Variablen zuweisen oder können Sie sie in einem `With`... `End With` Block.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="ff2c3-106">Um den Zugriff auf ein stark qualifiziertes Objekt beschleunigen durch eine Variable zuweisen</span><span class="sxs-lookup"><span data-stu-id="ff2c3-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1.  <span data-ttu-id="ff2c3-107">Deklarieren Sie eine Variable des Typs des Objekts, das Sie häufig zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="ff2c3-108">Geben Sie den Qualifizierungspfad im Initialisierungsteil der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="ff2c3-109">Verwenden Sie die Variable, um die Member des Objekts zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="ff2c3-110">Um den Zugriff auf ein stark qualifiziertes Objekt beschleunigen mithilfe einer With... End-With-block</span><span class="sxs-lookup"><span data-stu-id="ff2c3-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1.  <span data-ttu-id="ff2c3-111">Fügen Sie den Qualifizierungspfad in einem `With` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="ff2c3-112">Zugriff auf die Member des Objekts in der `With` blockieren, bevor die `End With` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="ff2c3-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ff2c3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff2c3-113">See also</span></span>

- [<span data-ttu-id="ff2c3-114">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="ff2c3-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="ff2c3-115">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ff2c3-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
