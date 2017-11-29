---
title: 'Gewusst wie: Auflisten installierter Schriftarten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bca536ed2f3e493e8d50fe8f1a0115327f1d8720
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="3ee78-102">Gewusst wie: Auflisten installierter Schriftarten</span><span class="sxs-lookup"><span data-stu-id="3ee78-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="3ee78-103">Die <xref:System.Drawing.Text.InstalledFontCollection> Klasse erbt von der <xref:System.Drawing.Text.FontCollection> abstrakte Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="3ee78-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="3ee78-104">Sie können eine <xref:System.Drawing.Text.InstalledFontCollection> auf dem Computer installierten Schriftarten aufzulistende Objekt.</span><span class="sxs-lookup"><span data-stu-id="3ee78-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="3ee78-105">Die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft ein <xref:System.Drawing.Text.InstalledFontCollection> Objekt ist ein Array von <xref:System.Drawing.FontFamily> Objekte.</span><span class="sxs-lookup"><span data-stu-id="3ee78-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ee78-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ee78-106">Example</span></span>  
 <span data-ttu-id="3ee78-107">Das folgende Beispiel listet die Namen aller Schriftartfamilien, die auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="3ee78-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="3ee78-108">Der Code Ruft die <xref:System.Drawing.FontFamily.Name%2A> -Eigenschaft jedes <xref:System.Drawing.FontFamily> Objekt in das zurückgegebene Array die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3ee78-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="3ee78-109">Wie die Namen der Produktfamilie abgerufen werden, werden sie eine durch Trennzeichen getrennte Liste verkettet.</span><span class="sxs-lookup"><span data-stu-id="3ee78-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="3ee78-110">Die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Klasse zeichnet eine durch Trennzeichen getrennte Liste die in einem Rechteck.</span><span class="sxs-lookup"><span data-stu-id="3ee78-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="3ee78-111">Wenn Sie den Beispielcode ausführen, wird die Ausgabe, die in der folgenden Abbildung dargestellten ähnlich sein.</span><span class="sxs-lookup"><span data-stu-id="3ee78-111">If you run the example code, the output will be similar to that shown in the following illustration.</span></span>  
  
 <span data-ttu-id="3ee78-112">![Installierte Schriftarten](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span><span class="sxs-lookup"><span data-stu-id="3ee78-112">![Installed Fonts](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3ee78-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3ee78-113">Compiling the Code</span></span>  
 <span data-ttu-id="3ee78-114">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.</span><span class="sxs-lookup"><span data-stu-id="3ee78-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="3ee78-115">Darüber hinaus sollten Sie importieren die <xref:System.Drawing.Text> Namespace.</span><span class="sxs-lookup"><span data-stu-id="3ee78-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ee78-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ee78-116">See Also</span></span>  
 [<span data-ttu-id="3ee78-117">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="3ee78-117">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
