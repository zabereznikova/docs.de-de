---
title: 'Gewusst wie: Verwenden der FontSizeConverter-Klasse'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe6988f21c2e40c65a7e8acd48727ab48bd58e05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-fontsizeconverter-class"></a><span data-ttu-id="43a6b-102">Gewusst wie: Verwenden der FontSizeConverter-Klasse</span><span class="sxs-lookup"><span data-stu-id="43a6b-102">How to: Use the FontSizeConverter Class</span></span>
## <a name="example"></a><span data-ttu-id="43a6b-103">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43a6b-103">Example</span></span>  
 <span data-ttu-id="43a6b-104">In diesem Beispiel wird gezeigt, wie zum Erstellen einer Instanz von <xref:System.Windows.FontSizeConverter> und verwenden, um die Schriftgröße zu ändern.</span><span class="sxs-lookup"><span data-stu-id="43a6b-104">This example shows how to create an instance of <xref:System.Windows.FontSizeConverter> and use it to change a font size.</span></span>  
  
 <span data-ttu-id="43a6b-105">Im Beispiel definiert eine benutzerdefinierte Methode mit dem Namen `changeSize` , konvertiert den Inhalt der eine <xref:System.Windows.Controls.ListBoxItem>, wie definiert in einer separaten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei, um eine Instanz von <xref:System.Double>, und höher in eine <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="43a6b-105">The example defines a custom method called `changeSize` that converts the contents of a <xref:System.Windows.Controls.ListBoxItem>, as defined in a separate [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file, to an instance of <xref:System.Double>, and later into a <xref:System.String>.</span></span> <span data-ttu-id="43a6b-106">Diese Methode übergibt der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.Windows.FontSizeConverter> -Objekt, das konvertiert der <xref:System.Windows.Controls.ContentControl.Content%2A> von einer <xref:System.Windows.Controls.ListBoxItem> mit einer Instanz von <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="43a6b-106">This method passes the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.Windows.FontSizeConverter> object, which converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of a <xref:System.Windows.Controls.ListBoxItem> to an instance of <xref:System.Double>.</span></span> <span data-ttu-id="43a6b-107">Dieser Wert wird dann wieder als Wert übergeben der <xref:System.Windows.Controls.TextBlock.FontSize%2A> Eigenschaft von der <xref:System.Windows.Controls.TextBlock> Element.</span><span class="sxs-lookup"><span data-stu-id="43a6b-107">This value is then passed back as the value of the <xref:System.Windows.Controls.TextBlock.FontSize%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="43a6b-108">In diesem Beispiel definiert auch eine zweite benutzerdefinierte Methode, die aufgerufen wird `changeFamily`.</span><span class="sxs-lookup"><span data-stu-id="43a6b-108">This example also defines a second custom method that is called `changeFamily`.</span></span> <span data-ttu-id="43a6b-109">Diese Methode konvertiert die <xref:System.Windows.Controls.ContentControl.Content%2A> von der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.String>, und übergibt dann diesen Wert auf die <xref:System.Windows.Controls.TextBlock.FontFamily%2A> Eigenschaft der <xref:System.Windows.Controls.TextBlock> Element.</span><span class="sxs-lookup"><span data-stu-id="43a6b-109">This method converts the <xref:System.Windows.Controls.ContentControl.Content%2A> of the <xref:System.Windows.Controls.ListBoxItem> to a <xref:System.String>, and then passes that value to the <xref:System.Windows.Controls.TextBlock.FontFamily%2A> property of the <xref:System.Windows.Controls.TextBlock> element.</span></span>  
  
 <span data-ttu-id="43a6b-110">Dieses Beispiel wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="43a6b-110">This example does not run.</span></span>  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="43a6b-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43a6b-111">See Also</span></span>  
 <xref:System.Windows.FontSizeConverter>
