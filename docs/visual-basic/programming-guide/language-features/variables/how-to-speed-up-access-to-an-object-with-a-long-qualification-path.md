---
title: 'Vorgehensweise: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: fe93e7bac2a21f1060d1f93765eb35e1ad0c7eb0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410411"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a><span data-ttu-id="f13bc-102">Gewusst wie: Beschleunigen des Zugriffs auf ein Objekt mit langem Qualifizierungspfad (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f13bc-102">How to: Speed Up Access to an Object with a Long Qualification Path (Visual Basic)</span></span>

<span data-ttu-id="f13bc-103">Wenn Sie häufig auf ein Objekt zugreifen, das einen Qualifizierungs Pfad mehrerer Methoden und Eigenschaften erfordert, können Sie den Code beschleunigen, indem Sie den Qualifikations Pfad nicht wiederholen.</span><span class="sxs-lookup"><span data-stu-id="f13bc-103">If you frequently access an object that requires a qualification path of several methods and properties, you can speed up your code by not repeating the qualification path.</span></span>

<span data-ttu-id="f13bc-104">Es gibt zwei Möglichkeiten, um das Wiederholen des Qualifizierungs Pfads zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f13bc-104">There are two ways you can avoid repeating the qualification path.</span></span> <span data-ttu-id="f13bc-105">Sie können das Objekt einer Variablen zuweisen, oder Sie können es in einem `With` ...- `End With` Block verwenden.</span><span class="sxs-lookup"><span data-stu-id="f13bc-105">You can assign the object to a variable, or you can use it in a `With`...`End With` block.</span></span>

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a><span data-ttu-id="f13bc-106">So beschleunigen Sie den Zugriff auf ein stark qualifiziertes Objekt, indem Sie es einer Variablen zuweisen</span><span class="sxs-lookup"><span data-stu-id="f13bc-106">To speed up access to a heavily qualified object by assigning it to a variable</span></span>

1. <span data-ttu-id="f13bc-107">Deklarieren Sie eine Variable des Typs des Objekts, auf das Sie häufig zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f13bc-107">Declare a variable of the type of the object that you are accessing frequently.</span></span> <span data-ttu-id="f13bc-108">Geben Sie den Qualifikations Pfad im Initialisierungs Teil der Deklaration an.</span><span class="sxs-lookup"><span data-stu-id="f13bc-108">Specify the qualification path in the initialization part of the declaration.</span></span>

    ```vb
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="f13bc-109">Verwenden Sie die-Variable, um auf die Member des-Objekts zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f13bc-109">Use the variable to access the object's members.</span></span>

    ```vb
    ctrlActv.Text = "Test"
    ctrlActv.Location = New Point(100, 100)
    ctrlActv.Show()
    ```

### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a><span data-ttu-id="f13bc-110">So beschleunigen Sie den Zugriff auf ein stark qualifiziertes Objekt mithilfe eines mit... Mit Block beenden</span><span class="sxs-lookup"><span data-stu-id="f13bc-110">To speed up access to a heavily qualified object by using a With...End With block</span></span>

1. <span data-ttu-id="f13bc-111">Legen Sie den Qualifikations Pfad in eine- `With` Anweisung ein.</span><span class="sxs-lookup"><span data-stu-id="f13bc-111">Put the qualification path in a `With` statement.</span></span>

    ```vb
    With someForm.ActiveForm.ActiveControl
    ```

2. <span data-ttu-id="f13bc-112">Greifen Sie auf die Member des-Objekts innerhalb des- `With` Blocks vor der- `End With` Anweisung zu.</span><span class="sxs-lookup"><span data-stu-id="f13bc-112">Access the object's members inside the `With` block, before the `End With` statement.</span></span>

    ```vb
        .Text = "Test"
        .Location = New Point(100, 100)
        .Show()
    End With
    ```

## <a name="see-also"></a><span data-ttu-id="f13bc-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f13bc-113">See also</span></span>

- [<span data-ttu-id="f13bc-114">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="f13bc-114">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="f13bc-115">With...End With-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f13bc-115">With...End With Statement</span></span>](../../../language-reference/statements/with-end-with-statement.md)
