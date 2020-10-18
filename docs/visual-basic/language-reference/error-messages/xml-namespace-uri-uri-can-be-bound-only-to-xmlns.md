---
title: XML-Namespace-URI ''<uri>'' kann nur an ''xmlns'' gebunden werden
ms.date: 07/20/2015
f1_keywords:
- bc31183
- vbc31183
helpviewer_keywords:
- BC31183
ms.assetid: 0ab1dbce-8397-4959-b2cd-f58798b051a0
ms.openlocfilehash: 1aec6ac0a354bfe7e0378a2e46a70a7161bf6d36
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163245"
---
# <a name="bc31183-xml-namespace-uri-httpwwww3orgxml1998namespace-can-be-bound-only-to-xmlns"></a><span data-ttu-id="c591c-102">BC31183: XML-Namespace-URI `http://www.w3.org/XML/1998/namespace` ; kann nur an ' xmlns ' gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="c591c-102">BC31183: XML namespace URI `http://www.w3.org/XML/1998/namespace`; can be bound only to 'xmlns'</span></span>

<span data-ttu-id="c591c-103">Der URI `http://www.w3.org/XML/1998/namespace` wird in einer XML-Namespace Deklaration verwendet.</span><span class="sxs-lookup"><span data-stu-id="c591c-103">The URI `http://www.w3.org/XML/1998/namespace` is used in an XML namespace declaration.</span></span> <span data-ttu-id="c591c-104">Dieser URI ist ein reservierter Namespace und kann nicht in einer XML-Namespace Deklaration enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="c591c-104">This URI is a reserved namespace and cannot be included in an XML namespace declaration.</span></span>

 <span data-ttu-id="c591c-105">**Fehler-ID:** BC31183</span><span class="sxs-lookup"><span data-stu-id="c591c-105">**Error ID:** BC31183</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c591c-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c591c-106">To correct this error</span></span>

<span data-ttu-id="c591c-107">Entfernen Sie die XML-Namespace Deklaration, oder ersetzen Sie den URI `http://www.w3.org/XML/1998/namespace` durch einen gültigen Namespace-URI.</span><span class="sxs-lookup"><span data-stu-id="c591c-107">Remove the XML namespace declaration or replace the URI `http://www.w3.org/XML/1998/namespace` with a valid namespace URI.</span></span>

## <a name="see-also"></a><span data-ttu-id="c591c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c591c-108">See also</span></span>

- [<span data-ttu-id="c591c-109">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="c591c-109">Imports Statement (XML Namespace)</span></span>](../statements/imports-statement-xml-namespace.md)
- [<span data-ttu-id="c591c-110">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="c591c-110">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="c591c-111">XML</span><span class="sxs-lookup"><span data-stu-id="c591c-111">XML</span></span>](../../programming-guide/language-features/xml/index.md)
