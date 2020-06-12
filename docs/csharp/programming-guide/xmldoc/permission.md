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
ms.openlocfilehash: bb7172042f0b472d03c3fa2d9dbd0d4d4265076b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287271"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="0489b-102">\<permission> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="0489b-102">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="0489b-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="0489b-103">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="0489b-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="0489b-104">Parameters</span></span>

- <span data-ttu-id="0489b-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="0489b-105">cref = " `member`"</span></span>

  <span data-ttu-id="0489b-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0489b-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="0489b-107">Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="0489b-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="0489b-108">*member* muss in doppelte Anführungszeichen (" ") gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="0489b-108">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="0489b-109">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [cref-Attribut](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="0489b-109">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

- `description`

  <span data-ttu-id="0489b-110">Eine Beschreibung des Zugriffs auf den Member</span><span class="sxs-lookup"><span data-stu-id="0489b-110">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="0489b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0489b-111">Remarks</span></span>

<span data-ttu-id="0489b-112">Mit dem `<permission>`-Tag können Sie den Zugriff auf einen Member dokumentieren.</span><span class="sxs-lookup"><span data-stu-id="0489b-112">The `<permission>` tag lets you document the access of a member.</span></span> <span data-ttu-id="0489b-113">Mit der <xref:System.Security.PermissionSet>-Klasse können Sie den Zugriff auf ein Member angeben.</span><span class="sxs-lookup"><span data-stu-id="0489b-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="0489b-114">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0489b-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="0489b-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0489b-115">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="0489b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0489b-116">See also</span></span>

- [<span data-ttu-id="0489b-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0489b-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="0489b-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="0489b-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
