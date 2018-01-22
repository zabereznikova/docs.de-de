---
title: Aspekte beim Hosten eines ActiveX-Steuerelements in Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 23c8476e4013cca6d906d85f11658deddc585869
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a><span data-ttu-id="58fe2-102">Aspekte beim Hosten eines ActiveX-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58fe2-102">Considerations When Hosting an ActiveX Control on a Windows Form</span></span>
<span data-ttu-id="58fe2-103">Obwohl Windows Forms zum Hosten von Windows Forms-Steuerelementen optimiert wurde, können Sie weiterhin ActiveX-Steuerelemente verwenden.</span><span class="sxs-lookup"><span data-stu-id="58fe2-103">Although Windows Forms have been optimized to host Windows Forms controls, you can still use ActiveX controls.</span></span> <span data-ttu-id="58fe2-104">Bei Verwendung von ActiveX-Steuerelementen in einer Anwendung sollten Sie Folgendes berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="58fe2-104">Keep the following considerations in mind when planning an application that uses ActiveX controls:</span></span>  
  
-   <span data-ttu-id="58fe2-105">**Sicherheit** Die Common Language Runtime wurde im Hinblick auf die Codezugriffssicherheit verbessert.</span><span class="sxs-lookup"><span data-stu-id="58fe2-105">**Security** The common language runtime has been enhanced with regard to code access security.</span></span> <span data-ttu-id="58fe2-106">Anwendungen mit Windows Forms können in einer voll vertrauenswürdigen Umgebung uneingeschränkt und in einer halb vertrauenswürdigen Umgebung mit Zugriff auf die meisten verfügbaren Funktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="58fe2-106">Applications featuring Windows Forms can run in a fully trusted environment without issue and in a semi-trusted environment with most of the functionality accessible.</span></span> <span data-ttu-id="58fe2-107">Windows Forms-Steuerelemente können problemlos in einem Browser integriert werden.</span><span class="sxs-lookup"><span data-stu-id="58fe2-107">Windows Forms controls can be hosted in a browser with no complications.</span></span> <span data-ttu-id="58fe2-108">Diese verbesserten Sicherheitsmerkmale können jedoch nicht genutzt werden, wenn ActiveX-Steuerelemente für Windows Forms verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58fe2-108">However, ActiveX controls on Windows Forms cannot take advantage of these security enhancements.</span></span> <span data-ttu-id="58fe2-109">Ausführen eines ActiveX-Steuerelements erfordert die Berechtigung für nicht verwalteten Code, mit festgelegt ist die <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="58fe2-109">Running an ActiveX control requires unmanaged code permission, which is set with the <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="58fe2-110">Weitere Informationen zu Sicherheit und die Berechtigung von nicht verwaltetem Code finden Sie unter <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="58fe2-110">For more information about security and unmanaged code permission, see <xref:System.Security.Permissions.SecurityPermissionAttribute>.</span></span>  
  
-   <span data-ttu-id="58fe2-111">**Gesamtkosten** ActiveX-Steuerelemente, die einem Windows Form hinzugefügt werden, werden komplett mit diesem Windows Form weitergegeben. Dadurch können die erstellten Dateien unter Umständen sehr groß werden.</span><span class="sxs-lookup"><span data-stu-id="58fe2-111">**Total Cost of Ownership** ActiveX controls added to a Windows Form are deployed with that Windows Form in their entirety, which can add significantly to the size of the file(s) created.</span></span> <span data-ttu-id="58fe2-112">Außerdem muss bei Verwendung von ActiveX-Steuerelementen für Windows Forms die Registrierung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="58fe2-112">Additionally, using ActiveX controls on Windows Forms requires writing to the registry.</span></span> <span data-ttu-id="58fe2-113">Damit wird stärker in den Computer des Benutzers eingegriffen als mit Windows Forms-Steuerelementen, bei denen dies nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="58fe2-113">This is more invasive to a user's computer than Windows Forms controls, which do not require this.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58fe2-114">Zum Arbeiten mit ActiveX-Steuerelementen ist ein COM-Interop-Wrapper erforderlich.</span><span class="sxs-lookup"><span data-stu-id="58fe2-114">Working with an ActiveX control requires the use of a COM interop wrapper.</span></span> <span data-ttu-id="58fe2-115">Weitere Informationen finden Sie unter [COM-Interoperabilität in Visual Basic und Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="58fe2-115">For more information, see [COM Interoperability in Visual Basic and Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="58fe2-116">Wenn der Name eines Members des ActiveX-Steuerelements einen im definierten Namen übereinstimmt, die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], der ActiveX Control Importer den Membernamen das Präfix wird **Ctl** beim Erstellen der <xref:System.Windows.Forms.AxHost> abgeleitete Klasse.</span><span class="sxs-lookup"><span data-stu-id="58fe2-116">If the name of a member of the ActiveX control matches a name defined in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], then the ActiveX Control Importer will prefix the member name with **Ctl** when it creates the <xref:System.Windows.Forms.AxHost> derived class.</span></span> <span data-ttu-id="58fe2-117">Wenn beispielsweise das ActiveX-Steuerelement ein Member mit dem Namen **Layout** enthält, wird dieser Name in der von AxHost abgeleiteten Klasse in **CtlLayout** geändert, da in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] das **Layout**-Ereignis bereits definiert ist.</span><span class="sxs-lookup"><span data-stu-id="58fe2-117">For example, if your ActiveX control has a member named **Layout**, it is renamed **CtlLayout** in the AxHost-derived class because the **Layout** event is defined within the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58fe2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58fe2-118">See Also</span></span>  
 [<span data-ttu-id="58fe2-119">Gewusst wie: Hinzufügen von ActiveX-Steuerelementen zu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58fe2-119">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="58fe2-120">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="58fe2-120">Code Access Security</span></span>](../../../../docs/framework/misc/code-access-security.md)  
 [<span data-ttu-id="58fe2-121">In zahlreichen Sprachen und Bibliotheken verglichene Steuerelemente und programmierbare Objekte</span><span class="sxs-lookup"><span data-stu-id="58fe2-121">Controls and Programmable Objects Compared in Various Languages and Libraries</span></span>](http://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [<span data-ttu-id="58fe2-122">Einfügen von Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58fe2-122">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [<span data-ttu-id="58fe2-123">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="58fe2-123">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)
