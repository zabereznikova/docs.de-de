---
title: 'Vorgehensweise: Auflisten installierter Schriftarten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 92f27399cce9e03a4679c8a34fbdafcf28c32252
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004110"
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="8552d-102">Vorgehensweise: Auflisten installierter Schriftarten</span><span class="sxs-lookup"><span data-stu-id="8552d-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="8552d-103">Die <xref:System.Drawing.Text.InstalledFontCollection> Klasse erbt von der <xref:System.Drawing.Text.FontCollection> abstrakte Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="8552d-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="8552d-104">Sie können eine <xref:System.Drawing.Text.InstalledFontCollection> Objekt, das auf dem Computer installierten Schriftarten aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="8552d-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="8552d-105">Die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft eine <xref:System.Drawing.Text.InstalledFontCollection> Objekt ist ein Array von <xref:System.Drawing.FontFamily> Objekte.</span><span class="sxs-lookup"><span data-stu-id="8552d-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8552d-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8552d-106">Example</span></span>  
 <span data-ttu-id="8552d-107">Das folgende Beispiel listet die Namen der Schriftfamilien alle auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="8552d-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="8552d-108">Der Code Ruft die <xref:System.Drawing.FontFamily.Name%2A> Eigenschaft der einzelnen <xref:System.Drawing.FontFamily> Objekt im Array zurückgegeben werden, indem die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8552d-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="8552d-109">Wie die Familiennamen abgerufen werden, werden sie eine durch Trennzeichen getrennte Liste verkettet.</span><span class="sxs-lookup"><span data-stu-id="8552d-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="8552d-110">Die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> zeichnen die durch Trennzeichen getrennte Liste in einem Rechteck.</span><span class="sxs-lookup"><span data-stu-id="8552d-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="8552d-111">Wenn Sie den Beispielcode ausführen, wird die Ausgabe ähnelt, die in der folgenden Abbildung dargestellt aussehen:</span><span class="sxs-lookup"><span data-stu-id="8552d-111">If you run the example code, the output will be similar to that shown in the following illustration:</span></span>  
  
 ![Screenshot mit der installierten Schriftfamilien.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8552d-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8552d-113">Compiling the Code</span></span>  
 <span data-ttu-id="8552d-114">Das obige Beispiel ist für die Verwendung mit Windows Forms konzipiert und erfordert <xref:System.Windows.Forms.PaintEventArgs> `e`, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8552d-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="8552d-115">Darüber hinaus sollten Sie importieren die <xref:System.Drawing.Text> Namespace.</span><span class="sxs-lookup"><span data-stu-id="8552d-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8552d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8552d-116">See also</span></span>

- [<span data-ttu-id="8552d-117">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="8552d-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
