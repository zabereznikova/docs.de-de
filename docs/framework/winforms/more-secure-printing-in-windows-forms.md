---
title: "Mehr Sicherheit beim Drucken in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b89a94fd0223d817b0dee37f7a3ed84dcbacbbec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="more-secure-printing-in-windows-forms"></a><span data-ttu-id="b9820-102">Mehr Sicherheit beim Drucken in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9820-102">More Secure Printing in Windows Forms</span></span>
<span data-ttu-id="b9820-103">Windows Forms-Anwendungen enthalten häufig drucken Fähigkeiten.</span><span class="sxs-lookup"><span data-stu-id="b9820-103">Windows Forms applications frequently include printing abilities.</span></span> <span data-ttu-id="b9820-104">Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] verwendet die <xref:System.Drawing.Printing.PrintingPermission> Klasse zum Steuern des Zugriffs auf Druckfunktionen und den zugehörigen <xref:System.Drawing.Printing.PrintingPermissionLevel> Enumerationswert, auf die Ebene des Zugriffs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b9820-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] uses the <xref:System.Drawing.Printing.PrintingPermission> class to control access to printing capabilities and the associated <xref:System.Drawing.Printing.PrintingPermissionLevel> enumeration value to indicate the level of access.</span></span> <span data-ttu-id="b9820-105">Drucken ist standardmäßig in den Zonen Lokales Intranet und Internet aktiviert; Allerdings ist die Ebene des Zugriffs in beiden Zonen eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="b9820-105">By default, printing is enabled by default in the Local Intranet and Internet zones; however, the level of access is restricted in both zones.</span></span> <span data-ttu-id="b9820-106">Ob Ihre Anwendung drucken kann, muss der Benutzer eingreifen, oder kann nicht drucken hängt von den Wert für die Berechtigung für die Anwendung gewährt.</span><span class="sxs-lookup"><span data-stu-id="b9820-106">Whether your application can print, requires user interaction, or cannot print depends upon the permission value granted to the application.</span></span> <span data-ttu-id="b9820-107">Standardmäßig erhält die lokalen Intranetzone <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> Zugriff und der Intranetzone empfängt <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> Zugriff.</span><span class="sxs-lookup"><span data-stu-id="b9820-107">By default, the Local Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> access and the Intranet zone receives <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> access.</span></span>  
  
 <span data-ttu-id="b9820-108">Die folgende Tabelle zeigt die verfügbaren Funktionen auf jeder Berechtigungsebene der drucken.</span><span class="sxs-lookup"><span data-stu-id="b9820-108">The following table shows the functionality available at each printing permission level.</span></span>  
  
|<span data-ttu-id="b9820-109">PrintingPermissionLevel</span><span class="sxs-lookup"><span data-stu-id="b9820-109">PrintingPermissionLevel</span></span>|<span data-ttu-id="b9820-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b9820-110">Description</span></span>|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|<span data-ttu-id="b9820-111">Bietet vollständigen Zugriff auf alle installierten Drucker.</span><span class="sxs-lookup"><span data-stu-id="b9820-111">Provides full access to all installed printers.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|<span data-ttu-id="b9820-112">Ermöglicht programmgesteuerten Drucken auf dem Standarddrucker und sicheres Drucken über ein eingeschränktes Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="b9820-112">Enables programmatic printing to the default printer and safer printing through a restrictive printing dialog box.</span></span> <span data-ttu-id="b9820-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span><span class="sxs-lookup"><span data-stu-id="b9820-113"><xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|<span data-ttu-id="b9820-114">Ermöglicht das Drucken nur über ein eingeschränktes Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="b9820-114">Provides printing only from a more-restricted dialog box.</span></span> <span data-ttu-id="b9820-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span><span class="sxs-lookup"><span data-stu-id="b9820-115"><xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.</span></span>|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|<span data-ttu-id="b9820-116">Verhindert den Zugriff auf Drucker.</span><span class="sxs-lookup"><span data-stu-id="b9820-116">Prevents access to printers.</span></span> <span data-ttu-id="b9820-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> ist eine Teilmenge von <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span><span class="sxs-lookup"><span data-stu-id="b9820-117"><xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> is a subset of <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9820-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9820-118">See Also</span></span>  
 [<span data-ttu-id="b9820-119">Mehr Sicherheit beim Datei- und Datenzugriff in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9820-119">More Secure File and Data Access in Windows Forms</span></span>](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [<span data-ttu-id="b9820-120">Weitere Überlegungen zur Sicherheit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9820-120">Additional Security Considerations in Windows Forms</span></span>](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [<span data-ttu-id="b9820-121">Übersicht über die Sicherheit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9820-121">Security in Windows Forms Overview</span></span>](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [<span data-ttu-id="b9820-122">Sicherheit in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b9820-122">Windows Forms Security</span></span>](../../../docs/framework/winforms/windows-forms-security.md)
