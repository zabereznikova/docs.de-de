---
title: 'Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 0a9dcd00d4bc3e64ae4fc9a1d4884fac18521825
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937968"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="a2600-102">Vorgehensweise: Erstellen von Schriftartfamilien und Schriftarten</span><span class="sxs-lookup"><span data-stu-id="a2600-102">How to: Construct Font Families and Fonts</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="a2600-103">Schriftarten mit dem gleichen Schriftart, aber verschiedene Formate gruppiert in Schriftfamilien.</span><span class="sxs-lookup"><span data-stu-id="a2600-103">groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="a2600-104">Die Familie der Schriftart Arial enthält beispielsweise die folgenden Schriftarten:</span><span class="sxs-lookup"><span data-stu-id="a2600-104">For example, the Arial font family contains the following fonts:</span></span>  
  
- <span data-ttu-id="a2600-105">Arial regulären</span><span class="sxs-lookup"><span data-stu-id="a2600-105">Arial Regular</span></span>  
  
- <span data-ttu-id="a2600-106">Arial fett</span><span class="sxs-lookup"><span data-stu-id="a2600-106">Arial Bold</span></span>  
  
- <span data-ttu-id="a2600-107">Arial kursiv</span><span class="sxs-lookup"><span data-stu-id="a2600-107">Arial Italic</span></span>  
  
- <span data-ttu-id="a2600-108">Arial fett kursiv</span><span class="sxs-lookup"><span data-stu-id="a2600-108">Arial Bold Italic</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="a2600-109">Mithilfe von vier Formaten Familien: Normal, fett, kursiv und fett kursiv.</span><span class="sxs-lookup"><span data-stu-id="a2600-109">uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="a2600-110">Adjektive, z. B. *eingrenzen* und *gerundet* Stile werden nicht berücksichtigt stattdessen werden sie Teil des Namens der Familie.</span><span class="sxs-lookup"><span data-stu-id="a2600-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="a2600-111">Arial breit genug ist z. B. eine Schriftfamilie mit den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="a2600-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
- <span data-ttu-id="a2600-112">Arial schmalen regulären</span><span class="sxs-lookup"><span data-stu-id="a2600-112">Arial Narrow Regular</span></span>  
  
- <span data-ttu-id="a2600-113">Arial Schmal Fett</span><span class="sxs-lookup"><span data-stu-id="a2600-113">Arial Narrow Bold</span></span>  
  
- <span data-ttu-id="a2600-114">Arial schmalen kursiv</span><span class="sxs-lookup"><span data-stu-id="a2600-114">Arial Narrow Italic</span></span>  
  
- <span data-ttu-id="a2600-115">Arial schmalen fett kursiv</span><span class="sxs-lookup"><span data-stu-id="a2600-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="a2600-116">Bevor Sie mit Text zeichnen können [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], müssen Sie erstellen eine <xref:System.Drawing.FontFamily> Objekt und ein <xref:System.Drawing.Font> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a2600-116">Before you can draw text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="a2600-117">Die <xref:System.Drawing.FontFamily> Objekt gibt an, die Schriftart (z. B. Arial), und die <xref:System.Drawing.Font> Objekt gibt an, die Größe, Stil und Einheiten.</span><span class="sxs-lookup"><span data-stu-id="a2600-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2600-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2600-118">Example</span></span>  
 <span data-ttu-id="a2600-119">Das folgende Beispiel erstellt einen regulären Stil Schriftart Arial mit einer Größe von 16 Pixel.</span><span class="sxs-lookup"><span data-stu-id="a2600-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="a2600-120">Im folgenden Code wird das erste Argument übergeben, um die <xref:System.Drawing.Font.%23ctor%2A> Konstruktor ist die <xref:System.Drawing.FontFamily> Objekt.</span><span class="sxs-lookup"><span data-stu-id="a2600-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="a2600-121">Das zweite Argument gibt an, die Größe der Schriftart in das vierte Argument identifizierte-Einheiten gemessen wird.</span><span class="sxs-lookup"><span data-stu-id="a2600-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="a2600-122">Das dritte Argument gibt den Stil an.</span><span class="sxs-lookup"><span data-stu-id="a2600-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="a2600-123"><xref:System.Drawing.GraphicsUnit.Pixel> ist ein Mitglied der <xref:System.Drawing.GraphicsUnit> -Enumeration und <xref:System.Drawing.FontStyle.Regular> ist ein Mitglied der <xref:System.Drawing.FontStyle> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a2600-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a2600-124">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="a2600-124">Compiling the Code</span></span>  
 <span data-ttu-id="a2600-125">Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs>`e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist.</span><span class="sxs-lookup"><span data-stu-id="a2600-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2600-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2600-126">See also</span></span>

- [<span data-ttu-id="a2600-127">Verwenden von Schriftarten und Text</span><span class="sxs-lookup"><span data-stu-id="a2600-127">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="a2600-128">Grafik und Zeichnen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a2600-128">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
