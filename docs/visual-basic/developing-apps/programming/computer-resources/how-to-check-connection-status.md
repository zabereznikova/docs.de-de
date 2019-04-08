---
title: 'Vorgehensweise: Überprüfen des Verbindungsstatus in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- Web connections [Visual Basic]
- IsAvailable property [Visual Basic], about IsAvailable
- connections [Visual Basic], checking status
- connection status [Visual Basic]
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
ms.openlocfilehash: fd618852c2d0650f168edf8dac53931216fc3a9b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826261"
---
# <a name="how-to-check-connection-status-in-visual-basic"></a><span data-ttu-id="7708a-102">Vorgehensweise: Überprüfen des Verbindungsstatus in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7708a-102">How to: Check Connection Status in Visual Basic</span></span>
<span data-ttu-id="7708a-103">Die <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>-Eigenschaft kann verwendet werden, um zu ermitteln, ob der Computer über eine funktionierende Netzwerk- oder Internetverbindung verfügt.</span><span class="sxs-lookup"><span data-stu-id="7708a-103">The <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable> property can be used to determine whether the computer has a working network or Internet connection.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-check-whether-a-computer-has-a-working-connection"></a><span data-ttu-id="7708a-104">So überprüfen Sie, ob ein Computer über eine funktionierende Verbindung verfügt</span><span class="sxs-lookup"><span data-stu-id="7708a-104">To check whether a computer has a working connection</span></span>  
  
-   <span data-ttu-id="7708a-105">Bestimmen Sie, ob die `IsAvailable`-Eigenschaft `True` oder `False` ist.</span><span class="sxs-lookup"><span data-stu-id="7708a-105">Determine whether the `IsAvailable` property is `True` or `False`.</span></span> <span data-ttu-id="7708a-106">Im folgende Code wird der Status der Eigenschaft überprüft und ausgegeben:</span><span class="sxs-lookup"><span data-stu-id="7708a-106">The following code checks the property's status and reports it:</span></span>  
  
     [!code-vb[VbResourceTasks#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#3)]  
  
     <span data-ttu-id="7708a-107">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7708a-107">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="7708a-108">In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden.</span><span class="sxs-lookup"><span data-stu-id="7708a-108">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="7708a-109">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="7708a-109">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7708a-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7708a-110">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable>
