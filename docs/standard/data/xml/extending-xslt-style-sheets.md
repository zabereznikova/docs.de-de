---
title: Erweitern von XSLT-Stylesheets
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df4ba2bf-a99e-4d22-bbf3-04fc67669dbc
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8ccd1a95586bc92bcc712639eded135a69da1a36
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="extending-xslt-style-sheets"></a><span data-ttu-id="c9ecd-102">Erweitern von XSLT-Stylesheets</span><span class="sxs-lookup"><span data-stu-id="c9ecd-102">Extending XSLT Style Sheets</span></span>
<span data-ttu-id="c9ecd-103">In diesem Abschnitt werden die verschiedenen Methoden zum Erweitern der XSLT-Funktionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c9ecd-103">This section describes the different methods of extending the XSLT functionality.</span></span> <span data-ttu-id="c9ecd-104">Mithilfe der <xref:System.Xml.Xsl.XsltArgumentList>-Klasse können Sie Erweiterungsobjekte oder Parameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c9ecd-104">You can add extension objects or parameters using the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span> <span data-ttu-id="c9ecd-105">Die Erweiterungsobjekte oder Parameter können dann aus dem Stylesheet aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c9ecd-105">The extension objects or parameters can then be called from the style sheet.</span></span> <span data-ttu-id="c9ecd-106">Darüber hinaus können Sie auch Skriptblöcke in das Stylesheet einbetten, indem Sie das `msxsl:script`-Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9ecd-106">In addition, you can also embed script blocks into the style sheet by using the `msxsl:script` element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9ecd-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c9ecd-107">In This Section</span></span>  
 [<span data-ttu-id="c9ecd-108">XSLT-Erweiterungsobjekte</span><span class="sxs-lookup"><span data-stu-id="c9ecd-108">XSLT Extension Objects</span></span>](../../../../docs/standard/data/xml/xslt-extension-objects.md)  
 <span data-ttu-id="c9ecd-109">Erläutert die Verwendung der <xref:System.Xml.Xsl.XsltArgumentList>-Klasse zum Verarbeiten von XSLT-Erweiterungsobjekten.</span><span class="sxs-lookup"><span data-stu-id="c9ecd-109">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT extension objects.</span></span>  
  
 [<span data-ttu-id="c9ecd-110">XSLT-Parameter</span><span class="sxs-lookup"><span data-stu-id="c9ecd-110">XSLT Parameters</span></span>](../../../../docs/standard/data/xml/xslt-parameters.md)  
 <span data-ttu-id="c9ecd-111">Erläutert die Verwendung der <xref:System.Xml.Xsl.XsltArgumentList>-Klasse zum Verarbeiten von XSLT-Parametern.</span><span class="sxs-lookup"><span data-stu-id="c9ecd-111">Discusses using the <xref:System.Xml.Xsl.XsltArgumentList> class to process XSLT parameters.</span></span>  
  
 [<span data-ttu-id="c9ecd-112">Skript-Blöcke verwenden msxsl: Script</span><span class="sxs-lookup"><span data-stu-id="c9ecd-112">Script Blocks Using msxsl:script</span></span>](../../../../docs/standard/data/xml/script-blocks-using-msxsl-script.md)  
 <span data-ttu-id="c9ecd-113">Erläutert die Verwendung des `msxsl:script`-Elements.</span><span class="sxs-lookup"><span data-stu-id="c9ecd-113">Discusses using the `msxsl:script` element.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c9ecd-114">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="c9ecd-114">Related Sections</span></span>  
 [<span data-ttu-id="c9ecd-115">XSLT Transformations (XSLT-Transformationen)</span><span class="sxs-lookup"><span data-stu-id="c9ecd-115">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
