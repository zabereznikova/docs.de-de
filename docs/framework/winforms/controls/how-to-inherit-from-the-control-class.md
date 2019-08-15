---
title: 'Vorgehensweise: Erben von der Control-Klasse'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
ms.openlocfilehash: 535827db660ab1113a25a01b7a0553a1c4414c74
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037788"
---
# <a name="how-to-inherit-from-the-control-class"></a><span data-ttu-id="6895b-102">Vorgehensweise: Erben von der Control-Klasse</span><span class="sxs-lookup"><span data-stu-id="6895b-102">How to: Inherit from the Control Class</span></span>
<span data-ttu-id="6895b-103">Wenn Sie ein vollständig benutzerdefiniertes Steuerelement erstellen möchten, das in einem Windows Form verwendet werden soll <xref:System.Windows.Forms.Control> , sollten Sie von der-Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="6895b-103">If you want to create a completely custom control to use on a Windows Form, you should inherit from the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="6895b-104">Obwohl die Vererbung von <xref:System.Windows.Forms.Control> der-Klasse erfordert, dass Sie mehr Planung und Implementierung durchführen, bietet Sie Ihnen auch die größte Palette von Optionen.</span><span class="sxs-lookup"><span data-stu-id="6895b-104">While inheriting from the <xref:System.Windows.Forms.Control> class requires that you perform more planning and implementation, it also provides you with the largest range of options.</span></span> <span data-ttu-id="6895b-105">Wenn Sie von <xref:System.Windows.Forms.Control>erben, erben Sie die grundlegende Funktionalität, mit der Steuerelemente funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6895b-105">When inheriting from <xref:System.Windows.Forms.Control>, you inherit the very basic functionality that makes controls work.</span></span> <span data-ttu-id="6895b-106">Die Funktionalität, die in <xref:System.Windows.Forms.Control> der-Klasse enthalten ist, verarbeitet Benutzereingaben über Tastatur und Maus, definiert die Begrenzungen und die Größe des Steuer Elements, stellt ein Windows-Handle bereit und bietet Nachrichten Behandlung und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="6895b-106">The functionality inherent in the <xref:System.Windows.Forms.Control> class handles user input through the keyboard and mouse, defines the bounds and size of the control, provides a windows handle, and provides message handling and security.</span></span> <span data-ttu-id="6895b-107">Sie enthält keine Zeichnungen, bei denen es sich in diesem Fall um das eigentliche Rendering der grafischen Benutzeroberfläche des Steuerelements handelt, und keine spezifische Funktionalität für Benutzerinteraktion.</span><span class="sxs-lookup"><span data-stu-id="6895b-107">It does not incorporate any painting, which in this case is the actual rendering of the graphical interface of the control, nor does it incorporate any specific user interaction functionality.</span></span> <span data-ttu-id="6895b-108">Sie müssen alle diese Aspekte über benutzerdefinierten Code bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6895b-108">You must provide all of these aspects through custom code.</span></span>

## <a name="to-create-a-custom-control"></a><span data-ttu-id="6895b-109">So erstellen Sie ein benutzerdefiniertes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6895b-109">To create a custom control</span></span>

1. <span data-ttu-id="6895b-110">Erstellen Sie ein neues **Windows-Anwendung** oder **Windows-Steuerelementbibliothek**-Projekt.</span><span class="sxs-lookup"><span data-stu-id="6895b-110">Create a new **Windows Application** or **Windows Control Library** project.</span></span>

2. <span data-ttu-id="6895b-111">Wählen Sie im Menü **Projekt** den Eintrag **Klasse hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="6895b-111">From the **Project** menu, choose **Add Class**.</span></span>

3. <span data-ttu-id="6895b-112">Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf **Benutzerdefiniertes Steuerelement**.</span><span class="sxs-lookup"><span data-stu-id="6895b-112">In the **Add New Item** dialog box, click **Custom Control**.</span></span>

     <span data-ttu-id="6895b-113">Ein neues benutzerdefiniertes Steuerelement wird zu Ihrem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6895b-113">A new custom control is added to your project.</span></span>

4. <span data-ttu-id="6895b-114">Drücken Sie F7, um den**Code-Editor** für das benutzerdefinierte Steuerelement zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6895b-114">Press F7 to open the **Code Editor** for your custom control.</span></span>

5. <span data-ttu-id="6895b-115"><xref:System.Windows.Forms.Control.OnPaint%2A> Suchen<xref:System.Windows.Forms.Control.OnPaint%2A> Sie die-Methode, die mit Ausnahme eines Aufrufes der-Methode der-Basisklasse leer ist.</span><span class="sxs-lookup"><span data-stu-id="6895b-115">Locate the <xref:System.Windows.Forms.Control.OnPaint%2A> method, which will be empty except for a call to the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class.</span></span>

6. <span data-ttu-id="6895b-116">Ändern Sie den Code so, dass er die gewünschte benutzerdefinierte Darstellung Ihres Steuerelements enthält.</span><span class="sxs-lookup"><span data-stu-id="6895b-116">Modify the code to incorporate any custom painting you want for your control.</span></span>

     <span data-ttu-id="6895b-117">Informationen zum Schreiben von Code zum Rendern von Grafiken für Steuerelemente finden Sie unter [Zeichnen und Ausgeben von benutzerdefinierten Steuerelementen](custom-control-painting-and-rendering.md).</span><span class="sxs-lookup"><span data-stu-id="6895b-117">For information about writing code to render graphics for controls, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>

7. <span data-ttu-id="6895b-118">Implementieren Sie alle benutzerdefinierten Methoden, Eigenschaften oder Ereignisse, die in das Steuerelement eingebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6895b-118">Implement any custom methods, properties, or events that your control will incorporate.</span></span>

8. <span data-ttu-id="6895b-119">Speichern und testen Sie das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="6895b-119">Save and test your control.</span></span>

## <a name="see-also"></a><span data-ttu-id="6895b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6895b-120">See also</span></span>

- [<span data-ttu-id="6895b-121">Varieties of Custom Controls (Vielfalt benutzerdefinierter Steuerelemente)</span><span class="sxs-lookup"><span data-stu-id="6895b-121">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="6895b-122">Vorgehensweise: Erben von der UserControl-Klasse</span><span class="sxs-lookup"><span data-stu-id="6895b-122">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="6895b-123">Vorgehensweise: Von vorhandenen Windows Forms Steuerelementen erben</span><span class="sxs-lookup"><span data-stu-id="6895b-123">How to: Inherit from Existing Windows Forms Controls</span></span>](how-to-inherit-from-existing-windows-forms-controls.md)
- [<span data-ttu-id="6895b-124">Vorgehensweise: Steuerelemente für Windows Forms erstellen</span><span class="sxs-lookup"><span data-stu-id="6895b-124">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="6895b-125">Problembehandlung für geerbte Ereignishandler in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6895b-125">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="6895b-126">Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="6895b-126">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
