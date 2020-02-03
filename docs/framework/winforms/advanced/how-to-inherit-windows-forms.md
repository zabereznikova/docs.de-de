---
title: Formular Vererbung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: cc3a4cc75fd13e8f193a6920ed5b4a9bc8fd5d74
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743322"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="e0020-102">Gewusst wie: Erben von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0020-102">How to: Inherit Windows Forms</span></span>

<span data-ttu-id="e0020-103">Das Erstellen neuer Windows Forms durch Vererbung der Eigenschaften der Basisformulare ist eine praktische Möglichkeit zum Duplizieren Ihrer Bemühungen, ohne ein Formular jedes Mal von Grund auf neu erstellen zu müssen, wenn Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="e0020-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>

<span data-ttu-id="e0020-104">Weitere Informationen zum Erben von Formularen zur Entwurfszeit mit dem Dialogfeld **Vererbungsauswahl** und zur visuellen Unterscheidung zwischen den Sicherheitsebenen der vererbten Steuerelemente finden Sie unter [Vorgehensweise: Erben von Formularen mithilfe des Dialogfelds „Vererbungsauswahl“](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="e0020-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e0020-105">Um von einem Formular zu erben, muss die Datei oder der Namespace, die dieses Formular enthalten, in eine ausführbare Datei oder DLL integriert werden.</span><span class="sxs-lookup"><span data-stu-id="e0020-105">In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="e0020-106">Wählen Sie zum Erstellen des Projekts aus dem Menü **Erstellen** die Option **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="e0020-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="e0020-107">Darüber hinaus muss der Klasse, die das Formular erbt, auch ein Verweis auf den Namespace hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e0020-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span>

## <a name="inherit-a-form-programmatically"></a><span data-ttu-id="e0020-108">Programm gesteuertes Erben eines Formulars</span><span class="sxs-lookup"><span data-stu-id="e0020-108">Inherit a form programmatically</span></span>

1. <span data-ttu-id="e0020-109">Fügen Sie in der Klasse einen Verweis zu dem Namespace hinzu, der das Formular enthält, das vererbt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e0020-109">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>

2. <span data-ttu-id="e0020-110">Fügen Sie in der Klassendefinition einen Verweis auf das Formular hinzu, das vererbt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e0020-110">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="e0020-111">Der Verweis sollte den Namespace enthalten, in dem sich das Formular befindet, gefolgt von einem Punkt und dem Namen des eigentlichen Formulars.</span><span class="sxs-lookup"><span data-stu-id="e0020-111">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>

    ```vb
    Public Class Form2
        Inherits Namespace1.Form1
    ```

    ```csharp
    public class Form2 : Namespace1.Form1
    ```

 <span data-ttu-id="e0020-112">Denken Sie beim Erben von Formularen daran, dass Probleme mit Ereignishandlern auftreten können, die zwei Mal aufgerufen werden, da jedes Ereignis sowohl von der Basisklasse als auch von der geerbten Klasse behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="e0020-112">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="e0020-113">Weitere Informationen dazu, wie Sie dieses Problem vermeiden können, finden Sie unter [Problembehandlung für geerbte Ereignishandler in Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="e0020-113">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0020-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0020-114">See also</span></span>

- [<span data-ttu-id="e0020-115">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e0020-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="e0020-116">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="e0020-116">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="e0020-117">using</span><span class="sxs-lookup"><span data-stu-id="e0020-117">using</span></span>](../../../csharp/language-reference/keywords/using.md)
- [<span data-ttu-id="e0020-118">Auswirkungen beim Ändern der Darstellung von Basisformularen</span><span class="sxs-lookup"><span data-stu-id="e0020-118">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="e0020-119">Visuelle Vererbung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0020-119">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
