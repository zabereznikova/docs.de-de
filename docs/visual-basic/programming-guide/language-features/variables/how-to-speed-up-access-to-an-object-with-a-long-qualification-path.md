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
ms.openlocfilehash: 94c838a69aab9fcae9dc0c79b6038ee90e2369e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769043"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="9f2f6-102">Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f2f6-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="9f2f6-103">Wenn Sie häufig ein Objekt, die einen Qualifizierungspfad, der mehrere Methoden und Eigenschaften erforderlich sind zugreifen, können Sie Ihren Code beschleunigen, indem nicht wiederholt den Qualifizierungspfad.</span><span class="sxs-lookup"><span data-stu-id="9f2f6-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="9f2f6-104">Es gibt zwei Möglichkeiten, die Sie vermeiden können, wiederholen den Qualifizierungspfad.</span><span class="sxs-lookup"><span data-stu-id="9f2f6-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="9f2f6-105">Sie können das Objekt einer Variablen zuweisen oder können Sie sie in einem `With`... `End With` Block.</span><span class="sxs-lookup"><span data-stu-id="9f2f6-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="9f2f6-106">Um den Zugriff auf ein stark qualifiziertes Objekt beschleunigen durch eine Variable zuweisen</span><span class="sxs-lookup"><span data-stu-id="9f2f6-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1. <span data-ttu-id="9f2f6-107">Deklarieren Sie eine Variable des Typs des Objekts, das Sie häufig zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9f2f6-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="9f2f6-108">Geben Sie den Qualifizierungspfad im Initialisierungsteil der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="9f2f6-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2. <span data-ttu-id="9f2f6-109">Verwenden Sie die Variable, um die Member des Objekts zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9f2f6-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="9f2f6-110">Um den Zugriff auf ein stark qualifiziertes Objekt beschleunigen mithilfe einer With... End-With-block</span><span class="sxs-lookup"><span data-stu-id="9f2f6-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1. <span data-ttu-id="9f2f6-111">Fügen Sie den Qualifizierungspfad in einem `With` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9f2f6-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2. <span data-ttu-id="9f2f6-112">Zugriff auf die Member des Objekts in der `With` blockieren, bevor die `End With` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9f2f6-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9f2f6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f2f6-113">See also</span></span>

- [<span data-ttu-id="9f2f6-114">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="9f2f6-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="9f2f6-115">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9f2f6-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
