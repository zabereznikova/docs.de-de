---
title: 'Gewusst wie: Erstellen von Ereignis Handlern zur Laufzeit'
description: Erfahren Sie, wie Sie einen Ereignishandler zur Laufzeit mit dem Windows Forms-Designer in Visual Studio erstellen. Diese Aktion ermöglicht Ihnen das Verbinden von Ereignis Handlern zur Laufzeit.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 857076c46377b3276154d9b193d4bbe51841828f
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325809"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a><span data-ttu-id="41959-104">Vorgehensweise: Erstellen von Ereignishandlern für Windows Forms zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="41959-104">How to: Create Event Handlers at Run Time for Windows Forms</span></span>

<span data-ttu-id="41959-105">Zusätzlich zum Erstellen von Ereignissen mithilfe des Windows Forms-Designer in Visual Studio können Sie auch einen Ereignishandler zur Laufzeit erstellen.</span><span class="sxs-lookup"><span data-stu-id="41959-105">In addition to creating events using the Windows Forms Designer in Visual Studio, you can also create an event handler at run time.</span></span> <span data-ttu-id="41959-106">Durch diese Aktion können Sie Ereignishandler basierend auf Bedingungen in Code zur Laufzeit miteinander verknüpfen, statt sie beim ersten Start des Programms miteinander zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="41959-106">This action allows you to connect event handlers based on conditions in code at run time as opposed to having them connected when the program initially starts.</span></span>

## <a name="create-an-event-handler-at-run-time"></a><span data-ttu-id="41959-107">Erstellen eines Ereignis Handlers zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="41959-107">Create an event handler at run time</span></span>

1. <span data-ttu-id="41959-108">Öffnen Sie das Formular, dem Sie einen Ereignishandler hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="41959-108">Open the form that you want to add an event handler to.</span></span>

2. <span data-ttu-id="41959-109">Fügen Sie eine Methode zu Ihrem Formular hinzu. Verwenden Sie hierfür die Methodensignatur für das Ereignis, das Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="41959-109">Add a method to your form with the method signature for the event that you want to handle.</span></span>

     <span data-ttu-id="41959-110">Wenn Sie z. b. das- <xref:System.Windows.Forms.Control.Click> Ereignis eines- <xref:System.Windows.Forms.Button> Steuer Elements verarbeitet haben, würden Sie eine Methode wie die folgende erstellen:</span><span class="sxs-lookup"><span data-stu-id="41959-110">For example, if you were handling the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control, you would create a method such as the following:</span></span>

    ```vb
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)
       ' Add event handler code here.
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
    // Add event handler code here.
    }
    ```

    ```cpp
    private:
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)
       {
          // Add event handler code here.
       }
    ```

3. <span data-ttu-id="41959-111">Fügen Sie für Ihre Anwendung geeigneten Code zum Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="41959-111">Add code to the event handler as appropriate to your application.</span></span>

4. <span data-ttu-id="41959-112">Bestimmen Sie, für welches Formular oder Steuerelement Sie einen Ereignishandler erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="41959-112">Determine which form or control you want to create an event handler for.</span></span>

5. <span data-ttu-id="41959-113">Fügen Sie in einer Methode innerhalb der Formularklasse einen Code hinzu, der den zu bearbeitenden Ereignishandler angibt.</span><span class="sxs-lookup"><span data-stu-id="41959-113">In a method within your form's class, add code that specifies the event handler to handle the event.</span></span> <span data-ttu-id="41959-114">Der folgende Code gibt z. b. an, dass der Ereignishandler `button1_Click` das- <xref:System.Windows.Forms.Control.Click> Ereignis eines-Steuer Elements behandelt <xref:System.Windows.Forms.Button> :</span><span class="sxs-lookup"><span data-stu-id="41959-114">For example, the following code specifies the event handler `button1_Click` handles the <xref:System.Windows.Forms.Control.Click> event of a <xref:System.Windows.Forms.Button> control:</span></span>

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     <span data-ttu-id="41959-115">Die <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> im obigen Visual Basic Code gezeigte-Methode legt einen Click-Ereignishandler für die Schaltfläche fest.</span><span class="sxs-lookup"><span data-stu-id="41959-115">The <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> method demonstrated in the Visual Basic code above establishes a click event handler for the button.</span></span>

## <a name="see-also"></a><span data-ttu-id="41959-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41959-116">See also</span></span>

- [<span data-ttu-id="41959-117">Erstellen von Ereignishandlern in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="41959-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="41959-118">Übersicht über Ereignishandler</span><span class="sxs-lookup"><span data-stu-id="41959-118">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)
- [<span data-ttu-id="41959-119">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="41959-119">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
