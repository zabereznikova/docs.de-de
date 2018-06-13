---
title: 'Gewusst wie: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: d52d13feb0f85065c0623b5937f558b841c036dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650198"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="bb4b3-102">Gewusst wie: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb4b3-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>
<span data-ttu-id="bb4b3-103">Wenn Sie häufig auf ein Objekt, die einen Qualifizierungspfad mehrere Methoden und Eigenschaften erforderlich sind zugreifen, können Sie den Code durch die Wiederholung nicht des Qualifizierungspfads beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="bb4b3-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>  
  
 <span data-ttu-id="bb4b3-104">Es gibt zwei Möglichkeiten, die Sie wiederholt den Qualifizierungspfad vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="bb4b3-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="bb4b3-105">Sie können das Objekt einer Variablen zuweisen oder können Sie ihn in ein `With`... `End With` Block.</span><span class="sxs-lookup"><span data-stu-id="bb4b3-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="bb4b3-106">Einrichten des Zugriffs an ein stark qualifiziertes Objekt beschleunigen, indem Sie einer Variablen zuweisen</span><span class="sxs-lookup"><span data-stu-id="bb4b3-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>  
  
1.  <span data-ttu-id="bb4b3-107">Deklarieren Sie eine Variable des Typs des Objekts, das Sie häufig zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bb4b3-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="bb4b3-108">Geben Sie den Qualifizierungspfad im Initialisierungsteil der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="bb4b3-108">Specify the qualification path in the initialization part of the declaration.</span></span>  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="bb4b3-109">Verwenden Sie die Variable, um die Member des Objekts zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bb4b3-109">Use the variable to access the object's members.</span></span>  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="bb4b3-110">Zugriff auf ein Objekt Qualifizierungspfad beschleunigen mithilfe ein With... End With-block</span><span class="sxs-lookup"><span data-stu-id="bb4b3-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>  
  
1.  <span data-ttu-id="bb4b3-111">Geben Sie den Qualifizierungspfad einer `With` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="bb4b3-111">Put the qualification path in a `With` statement.</span></span>  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  <span data-ttu-id="bb4b3-112">Zugriff auf Member des Objekts innerhalb der `With` -Block vor der `End With` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="bb4b3-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bb4b3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb4b3-113">See Also</span></span>  
 [<span data-ttu-id="bb4b3-114">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="bb4b3-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="bb4b3-115">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bb4b3-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
