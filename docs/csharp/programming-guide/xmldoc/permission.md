---
title: <permission> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 4f76d28d5531c1b9f01fa950589407934cc1244a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77093473"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="c1680-102">\<permission> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="c1680-102">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="c1680-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1680-103">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="c1680-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="c1680-104">Parameters</span></span>

- <span data-ttu-id="c1680-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="c1680-105">cref = " `member`"</span></span>

  <span data-ttu-id="c1680-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c1680-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="c1680-107">Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="c1680-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="c1680-108">*member* muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="c1680-108">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="c1680-109">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [cref-Attribut](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="c1680-109">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

- `description`

  <span data-ttu-id="c1680-110">Eine Beschreibung des Zugriffs auf den Member</span><span class="sxs-lookup"><span data-stu-id="c1680-110">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1680-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1680-111">Remarks</span></span>

<span data-ttu-id="c1680-112">Mit dem \<permission>-Tag können Sie den Zugriff auf einen Member dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="c1680-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="c1680-113">Mit der <xref:System.Security.PermissionSet>-Klasse können Sie den Zugriff auf ein Member angeben.</span><span class="sxs-lookup"><span data-stu-id="c1680-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="c1680-114">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c1680-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="c1680-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1680-115">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="c1680-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1680-116">See also</span></span>

- [<span data-ttu-id="c1680-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c1680-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="c1680-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="c1680-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
