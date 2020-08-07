---
title: <permission> – C#-Programmierhandbuch
description: Erfahren Sie mehr über das XML-Tag <permission> ein. Mit diesem Tag können Sie den Zugriff auf einen Member dokumentieren. Die PermissionSet-Klasse ermöglicht die Angabe des Zugriffs auf einen Member.
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 38c87505b8b2973875e474ffd296dc02b7fb9de6
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381722"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="d39fc-105">\<permission> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d39fc-105">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="d39fc-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d39fc-106">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="d39fc-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d39fc-107">Parameters</span></span>

- <span data-ttu-id="d39fc-108">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="d39fc-108">cref = " `member`"</span></span>

  <span data-ttu-id="d39fc-109">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d39fc-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="d39fc-110">Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="d39fc-110">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="d39fc-111">*member* muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="d39fc-111">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="d39fc-112">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [cref-Attribut](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="d39fc-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

- `description`

  <span data-ttu-id="d39fc-113">Eine Beschreibung des Zugriffs auf den Member</span><span class="sxs-lookup"><span data-stu-id="d39fc-113">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="d39fc-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d39fc-114">Remarks</span></span>

<span data-ttu-id="d39fc-115">Mit dem `<permission>`-Tag können Sie den Zugriff auf einen Member dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="d39fc-115">The `<permission>` tag lets you document the access of a member.</span></span> <span data-ttu-id="d39fc-116">Mit der <xref:System.Security.PermissionSet>-Klasse können Sie den Zugriff auf ein Member angeben.</span><span class="sxs-lookup"><span data-stu-id="d39fc-116">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="d39fc-117">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="d39fc-117">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="d39fc-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d39fc-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="d39fc-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d39fc-119">See also</span></span>

- [<span data-ttu-id="d39fc-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d39fc-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="d39fc-121">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="d39fc-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
