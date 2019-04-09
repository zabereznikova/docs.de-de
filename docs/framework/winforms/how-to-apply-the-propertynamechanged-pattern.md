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
ms.openlocfilehash: 36670eee6235277a7fe98770192df9ae05d3dd03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213024"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="0a58c-102">Vorgehensweise: Anwenden des PropertyNameChanged-Musters</span><span class="sxs-lookup"><span data-stu-id="0a58c-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="0a58c-103">Im folgenden Codebeispiel wird veranschaulicht, wie zum Anwenden der *PropertyName*Changed-Muster in ein benutzerdefiniertes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="0a58c-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="0a58c-104">Wenden Sie dieses Muster, wenn Sie benutzerdefinierte Steuerelemente implementieren, die mit der Windows Forms Datenbindungs-Engine verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a58c-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a58c-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0a58c-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0a58c-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0a58c-106">Compiling the Code</span></span>  
 <span data-ttu-id="0a58c-107">Um das vorherige Codebeispiel zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="0a58c-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="0a58c-108">Fügen Sie den Code in eine leere Codedatei ein.</span><span class="sxs-lookup"><span data-stu-id="0a58c-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="0a58c-109">Sie müssen das benutzerdefinierte Steuerelement in einem Windows Form, die enthält verwenden eine `Main` Methode.</span><span class="sxs-lookup"><span data-stu-id="0a58c-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a58c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a58c-110">See also</span></span>

- [<span data-ttu-id="0a58c-111">Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a58c-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="0a58c-112">Änderungsbenachrichtigung in der Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="0a58c-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="0a58c-113">Datenbindung in Web Forms</span><span class="sxs-lookup"><span data-stu-id="0a58c-113">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
