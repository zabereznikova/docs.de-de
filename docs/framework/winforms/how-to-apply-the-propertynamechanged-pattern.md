---
title: 'Gewusst wie: Anwenden des PropertyNameChanged-Musters'
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
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1afe397a92ac6e79e84757baa0c41f6e0c54b7f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="fbd6f-102">Gewusst wie: Anwenden des PropertyNameChanged-Musters</span><span class="sxs-lookup"><span data-stu-id="fbd6f-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="fbd6f-103">Das folgende Codebeispiel veranschaulicht das Anwenden der *PropertyName*-Muster auf ein benutzerdefiniertes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fbd6f-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="fbd6f-104">Wenden Sie dieses Muster, wenn Sie benutzerdefinierte Steuerelemente implementieren, die mit der Windows Forms-Datenbindungsmodul verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fbd6f-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbd6f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbd6f-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fbd6f-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="fbd6f-106">Compiling the Code</span></span>  
 <span data-ttu-id="fbd6f-107">So kompilieren Sie das vorherige Codebeispiel:</span><span class="sxs-lookup"><span data-stu-id="fbd6f-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="fbd6f-108">Fügen Sie den Code in eine leere Codedatei ein.</span><span class="sxs-lookup"><span data-stu-id="fbd6f-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="fbd6f-109">Sie müssen das benutzerdefinierte Steuerelement in einem Windows Form, die enthält verwenden eine `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="fbd6f-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd6f-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbd6f-110">See Also</span></span>  
 [<span data-ttu-id="fbd6f-111">Gewusst wie: Implementieren der INotifyPropertyChanged-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fbd6f-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 [<span data-ttu-id="fbd6f-112">Änderungsbenachrichtigung in der Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="fbd6f-112">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="fbd6f-113">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="fbd6f-113">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
