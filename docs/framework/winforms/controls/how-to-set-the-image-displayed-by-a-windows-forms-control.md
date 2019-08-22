---
title: 'Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Bildes'
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Button control [Windows Forms], images
- Windows Forms controls, images
- controls [Windows Forms], images
- images [Windows Forms], Windows Forms controls
- examples [Windows Forms], controls
ms.assetid: 9445af8f-4f62-48b0-a3f6-068058964b9f
ms.openlocfilehash: b1b1dbbb50c3b19cf8d8a7d7030d0bc168afb6a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666185"
---
# <a name="how-to-set-the-image-displayed-by-a-windows-forms-control"></a><span data-ttu-id="5236a-102">Vorgehensweise: Festlegen des von einem Windows Forms Steuerelement angezeigten Bilds</span><span class="sxs-lookup"><span data-stu-id="5236a-102">How to: Set the image displayed by a Windows Forms control</span></span>

<span data-ttu-id="5236a-103">Mehrere Windows Forms Steuerelemente können Bilder anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5236a-103">Several Windows Forms controls can display images.</span></span> <span data-ttu-id="5236a-104">Diese Bilder können Symbole sein, die den Zweck des Steuer Elements verdeutlichen, wie z. b. ein Diskettensymbol auf einer Schaltfläche, die den Befehl "Speichern" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="5236a-104">These images can be icons that clarify the purpose of the control, such as a diskette icon on a button denoting the Save command.</span></span> <span data-ttu-id="5236a-105">Alternativ können die Symbole Hintergrundbilder sein, um dem Steuerelement das gewünschte Aussehen und Verhalten zu geben.</span><span class="sxs-lookup"><span data-stu-id="5236a-105">Alternatively, the icons can be background images to give the control the appearance and behavior you want.</span></span>

## <a name="programmatic"></a><span data-ttu-id="5236a-106">Programmgesteuerten</span><span class="sxs-lookup"><span data-stu-id="5236a-106">Programmatic</span></span>

<span data-ttu-id="5236a-107">Legen Sie die- `Image` Eigenschaft `BackgroundImage` oder-Eigenschaft des Steuer Elements <xref:System.Drawing.Image>auf ein Objekt vom Typ fest.</span><span class="sxs-lookup"><span data-stu-id="5236a-107">Set the control's `Image` or `BackgroundImage` property to an object of type <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="5236a-108">Im allgemeinen laden Sie das Bild mithilfe der <xref:System.Drawing.Image.FromFile%2A> -Methode aus einer Datei.</span><span class="sxs-lookup"><span data-stu-id="5236a-108">Generally, you'll be loading the image from a file by using the <xref:System.Drawing.Image.FromFile%2A> method.</span></span>

<span data-ttu-id="5236a-109">Im folgenden Codebeispiel ist der Pfad, der für den Speicherort des Bilds festgelegt wurde, der Ordner **eigene Bilder** .</span><span class="sxs-lookup"><span data-stu-id="5236a-109">In the following code example, the path set for the location of the image is the **My Pictures** folder.</span></span> <span data-ttu-id="5236a-110">Die meisten Computer unter dem Windows-Betriebssystem enthalten dieses Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="5236a-110">Most computers running the Windows operating system include this directory.</span></span> <span data-ttu-id="5236a-111">Dies ermöglicht es Benutzern mit minimalen System Zugriffsebenen, die Anwendung sicher auszuführen.</span><span class="sxs-lookup"><span data-stu-id="5236a-111">This also enables users with minimal system access levels to run the application safely.</span></span> <span data-ttu-id="5236a-112">Im folgenden Codebeispiel ist es erforderlich, dass Sie bereits über ein <xref:System.Windows.Forms.PictureBox> Formular mit einem hinzugefügten Steuerelement verfügen.</span><span class="sxs-lookup"><span data-stu-id="5236a-112">The following code example requires that you already have a form with a <xref:System.Windows.Forms.PictureBox> control added.</span></span>

```vb
' Replace the image named below with your own icon.
PictureBox1.Image = Image.FromFile _
   (System.Environment.GetFolderPath _
   (System.Environment.SpecialFolder.MyPictures) _
   & "\Image.gif")
```

```csharp
// Replace the image named below with your own icon.
// Note the escape character used (@) when specifying the path.
pictureBox1.Image = Image.FromFile
   (System.Environment.GetFolderPath
   (System.Environment.SpecialFolder.MyPictures)
   + @"\Image.gif");
```

```cpp
// Replace the image named below with your own icon.
pictureBox1->Image = Image::FromFile(String::Concat
   (System::Environment::GetFolderPath
   (System::Environment::SpecialFolder::MyPictures),
   "\\Image.gif"));
```

## <a name="designer"></a><span data-ttu-id="5236a-113">Designer</span><span class="sxs-lookup"><span data-stu-id="5236a-113">Designer</span></span>

1. <span data-ttu-id="5236a-114">Wählen Sie im **Eigenschaften** Fenster von Visual Studio die **Bild** -oder **BackgroundImage** -Eigenschaft des Steuer Elements aus, und klicken Sie dann auf![die Schaltfläche mit den Auslassungs Zeichen (Ellipsen in Visual Studio](./media/visual-studio-ellipsis-button.png)), um die **Auswahl** Dialogfeld Ressource.</span><span class="sxs-lookup"><span data-stu-id="5236a-114">In the **Properties** window of Visual Studio, select the **Image** or **BackgroundImage** property of the control, and then select the ellipsis (![Ellipsis button in Visual Studio](./media/visual-studio-ellipsis-button.png)) to display the **Select Resource** dialog box.</span></span>

2. <span data-ttu-id="5236a-115">Wählen Sie das Abbild aus, das Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="5236a-115">Select the image you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="5236a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5236a-116">See also</span></span>

- <xref:System.Drawing.Image.FromFile%2A>
- <xref:System.Drawing.Image>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
