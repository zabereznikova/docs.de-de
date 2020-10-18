---
title: Die XML-Achseneigenschaften unterstützen keine späte Bindung
ms.date: 07/20/2015
f1_keywords:
- bc31168
- vbc31168
helpviewer_keywords:
- BC31168
ms.assetid: 45707363-55e4-4151-892d-d8729106355b
ms.openlocfilehash: 9eef245d6f83770ce26bc9e753711543241d57fb
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163284"
---
# <a name="bc31168-xml-axis-properties-do-not-support-late-binding"></a><span data-ttu-id="aa873-102">BC31168: die XML-Achsen Eigenschaften unterstützen keine späte Bindung.</span><span class="sxs-lookup"><span data-stu-id="aa873-102">BC31168: XML axis properties do not support late binding</span></span>

<span data-ttu-id="aa873-103">Für ein nicht typisiertes Objekt wurde auf eine XML-Achsen Eigenschaft verwiesen.</span><span class="sxs-lookup"><span data-stu-id="aa873-103">An XML axis property has been referenced for an untyped object.</span></span>

 <span data-ttu-id="aa873-104">**Fehler-ID:** BC31168</span><span class="sxs-lookup"><span data-stu-id="aa873-104">**Error ID:** BC31168</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="aa873-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="aa873-105">To correct this error</span></span>

- <span data-ttu-id="aa873-106">Stellen Sie sicher, dass das Objekt ein stark typisiertes Objekt ist, bevor Sie auf <xref:System.Xml.Linq.XElement> die XML-Achsen Eigenschaft verweisen.</span><span class="sxs-lookup"><span data-stu-id="aa873-106">Ensure that the object is a strong-typed <xref:System.Xml.Linq.XElement> object before referencing the XML axis property.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa873-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa873-107">See also</span></span>

- [<span data-ttu-id="aa873-108">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="aa873-108">XML Axis Properties</span></span>](../xml-axis/index.md)
- [<span data-ttu-id="aa873-109">XML</span><span class="sxs-lookup"><span data-stu-id="aa873-109">XML</span></span>](../../programming-guide/language-features/xml/index.md)
