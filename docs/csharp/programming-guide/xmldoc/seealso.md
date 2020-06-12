---
title: <seealso> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: 1b801ac1b5a0a59d97ccc35ec78930d99223e846
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287219"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="464a1-102">\<seealso> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="464a1-102">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="464a1-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="464a1-103">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="464a1-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="464a1-104">Parameters</span></span>

- <span data-ttu-id="464a1-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="464a1-105">cref = " `member`"</span></span>

  <span data-ttu-id="464a1-106">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="464a1-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="464a1-107">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.`member`</span><span class="sxs-lookup"><span data-stu-id="464a1-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="464a1-108">muss in doppelte Anführungszeichen („“) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="464a1-108">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="464a1-109">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [cref-Attribut](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="464a1-109">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="464a1-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="464a1-110">Remarks</span></span>

<span data-ttu-id="464a1-111">Mit dem `<seealso>`-Tag kann der Text angegeben werden, der im Abschnitt „Siehe auch“ angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="464a1-111">The `<seealso>` tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="464a1-112">Mit [\<see>](./see.md) kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="464a1-112">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="464a1-113">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="464a1-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="464a1-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="464a1-114">Example</span></span>

<span data-ttu-id="464a1-115">Unter [\<summary>](./summary.md) finden Sie ein Beispiel für die Verwendung von \<seealso>.</span><span class="sxs-lookup"><span data-stu-id="464a1-115">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="464a1-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="464a1-116">See also</span></span>

- [<span data-ttu-id="464a1-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="464a1-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="464a1-118">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="464a1-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
