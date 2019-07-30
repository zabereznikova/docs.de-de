---
title: 'Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit einem langen Qualifizierungs Pfad (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: a8e50a2ed04037b48091321dc0c9ac2ea1db35f4
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631097"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="f9081-102">Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit einem langen Qualifizierungs Pfad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f9081-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>

<span data-ttu-id="f9081-103">Wenn Sie häufig auf ein Objekt zugreifen, das einen Qualifizierungs Pfad mehrerer Methoden und Eigenschaften erfordert, können Sie den Code beschleunigen, indem Sie den Qualifikations Pfad nicht wiederholen.</span><span class="sxs-lookup"><span data-stu-id="f9081-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>

<span data-ttu-id="f9081-104">Es gibt zwei Möglichkeiten, um das Wiederholen des Qualifizierungs Pfads zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f9081-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="f9081-105">Sie können das Objekt einer Variablen zuweisen, oder Sie können es in einem `With`... `End With` blockieren.</span><span class="sxs-lookup"><span data-stu-id="f9081-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="f9081-106">So beschleunigen Sie den Zugriff auf ein stark qualifiziertes Objekt, indem Sie es einer Variablen zuweisen</span><span class="sxs-lookup"><span data-stu-id="f9081-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>

1. <span data-ttu-id="f9081-107">Deklarieren Sie eine Variable des Typs des Objekts, auf das Sie häufig zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f9081-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="f9081-108">Geben Sie den Qualifikations Pfad im Initialisierungs Teil der Deklaration an.</span><span class="sxs-lookup"><span data-stu-id="f9081-108">Specify the qualification path in the initialization part of the declaration.</span></span>

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="f9081-109">Verwenden Sie die-Variable, um auf die Member des-Objekts zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f9081-109">Use the variable to access the object's members.</span></span>

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="f9081-110">So beschleunigen Sie den Zugriff auf ein stark qualifiziertes Objekt mithilfe eines mit... Mit Block beenden</span><span class="sxs-lookup"><span data-stu-id="f9081-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>

1. <span data-ttu-id="f9081-111">Legen Sie den Qualifikations Pfad in `With` eine-Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="f9081-111">Put the qualification path in a `With` statement.</span></span>

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="f9081-112">Greifen Sie auf die Member des- `With` Objekts innerhalb des- `End With` Blocks vor der-Anweisung zu.</span><span class="sxs-lookup"><span data-stu-id="f9081-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a><span data-ttu-id="f9081-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9081-113">See also</span></span>

- [<span data-ttu-id="f9081-114">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="f9081-114">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="f9081-115">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f9081-115">With...End With Statement</span></span>](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
