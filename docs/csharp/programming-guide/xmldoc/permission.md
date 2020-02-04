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
ms.openlocfilehash: 14abb5bd181f401a4e6834d110e20fa920566580
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789736"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="887ce-102">\<permission> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="887ce-102">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="887ce-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="887ce-103">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="887ce-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="887ce-104">Parameters</span></span>

- <span data-ttu-id="887ce-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="887ce-105">cref = " `member`"</span></span>

  <span data-ttu-id="887ce-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="887ce-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="887ce-107">Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="887ce-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="887ce-108">*member* muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="887ce-108">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="887ce-109">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="887ce-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>

- `description`

  <span data-ttu-id="887ce-110">Eine Beschreibung des Zugriffs auf den Member</span><span class="sxs-lookup"><span data-stu-id="887ce-110">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="887ce-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="887ce-111">Remarks</span></span>

<span data-ttu-id="887ce-112">Mit dem \<permission>-Tag können Sie den Zugriff auf einen Member dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="887ce-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="887ce-113">Mit der <xref:System.Security.PermissionSet>-Klasse können Sie den Zugriff auf ein Member angeben.</span><span class="sxs-lookup"><span data-stu-id="887ce-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="887ce-114">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="887ce-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="887ce-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="887ce-115">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="887ce-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="887ce-116">See also</span></span>

- [<span data-ttu-id="887ce-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="887ce-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="887ce-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="887ce-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
