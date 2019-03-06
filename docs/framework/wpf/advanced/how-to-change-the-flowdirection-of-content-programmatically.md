---
title: 'Vorgehensweise: Programmgesteuertes Ändern der FlowDirection des Inhalts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359327"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="ec655-102">Vorgehensweise: Programmgesteuertes Ändern der FlowDirection des Inhalts</span><span class="sxs-lookup"><span data-stu-id="ec655-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="ec655-103">Dieses Beispiel zeigt, wie Sie programmgesteuert ändern der <xref:System.Windows.FrameworkElement.FlowDirection%2A> Eigenschaft eine <xref:System.Windows.Controls.FlowDocumentReader>.</span><span class="sxs-lookup"><span data-stu-id="ec655-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec655-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec655-104">Example</span></span>  
 <span data-ttu-id="ec655-105">Zwei <xref:System.Windows.Controls.Button> Elemente erstellt werden, jeweils eine der möglichen Werte des <xref:System.Windows.FlowDirection>.</span><span class="sxs-lookup"><span data-stu-id="ec655-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="ec655-106">Wenn eine Schaltfläche geklickt wird, wird der zugehörige Eigenschaftswert auf den Inhalt angewendet eine <xref:System.Windows.Controls.FlowDocumentReader> mit dem Namen `tf1`.</span><span class="sxs-lookup"><span data-stu-id="ec655-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="ec655-107">Den Wert der Eigenschaft werden auch in geschrieben eine <xref:System.Windows.Controls.TextBlock> mit dem Namen `txt1`.</span><span class="sxs-lookup"><span data-stu-id="ec655-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="ec655-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec655-108">Example</span></span>  
 <span data-ttu-id="ec655-109">Die Ereignisse im Zusammenhang mit den oben definierten Klicks auf Schaltflächen werden verarbeitet, einem C# Code-Behind-Datei.</span><span class="sxs-lookup"><span data-stu-id="ec655-109">The events associated with the button clicks defined above are handled in a C# code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
