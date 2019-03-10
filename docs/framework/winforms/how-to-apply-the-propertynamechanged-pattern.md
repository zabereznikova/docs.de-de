---
title: 'Vorgehensweise: Anwenden des PropertyNameChanged-Musters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 889a7f5f7a84db378acaa88b717b6011f1a3dfdc
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703477"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="174af-102">Vorgehensweise: Anwenden des PropertyNameChanged-Musters</span><span class="sxs-lookup"><span data-stu-id="174af-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="174af-103">Im folgenden Codebeispiel wird veranschaulicht, wie zum Anwenden der *PropertyName*Changed-Muster in ein benutzerdefiniertes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="174af-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="174af-104">Wenden Sie dieses Muster, wenn Sie benutzerdefinierte Steuerelemente implementieren, die mit der Windows Forms Datenbindungs-Engine verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="174af-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="174af-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="174af-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="174af-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="174af-106">Compiling the Code</span></span>  
 <span data-ttu-id="174af-107">Um das vorherige Codebeispiel zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="174af-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="174af-108">Fügen Sie den Code in eine leere Codedatei ein.</span><span class="sxs-lookup"><span data-stu-id="174af-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="174af-109">Sie müssen das benutzerdefinierte Steuerelement in einem Windows Form, die enthält verwenden eine `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="174af-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="174af-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="174af-110">See also</span></span>
- [<span data-ttu-id="174af-111">Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="174af-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="174af-112">Änderungsbenachrichtigung in der Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="174af-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="174af-113">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="174af-113">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
