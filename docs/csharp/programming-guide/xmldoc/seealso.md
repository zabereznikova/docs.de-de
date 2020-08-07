---
title: <seealso> – C#-Programmierhandbuch
description: Erfahren Sie, mehr über das XML-Tag <seealso> ein. Mit diesem Tag können Sie den Text angeben, der im Abschnitt „Siehe auch“ angezeigt werden sollen.
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
ms.openlocfilehash: e8618ef352a4fa7f0fd4c88733c6568b0e12e376
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380643"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="3f23a-105">\<seealso> (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3f23a-105">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="3f23a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f23a-106">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="3f23a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="3f23a-107">Parameters</span></span>

- <span data-ttu-id="3f23a-108">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="3f23a-108">cref = " `member`"</span></span>

  <span data-ttu-id="3f23a-109">Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="3f23a-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="3f23a-110">Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe.`member`</span><span class="sxs-lookup"><span data-stu-id="3f23a-110">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="3f23a-111">muss in doppelte Anführungszeichen („“) gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="3f23a-111">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="3f23a-112">Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [cref-Attribut](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="3f23a-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="3f23a-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3f23a-113">Remarks</span></span>

<span data-ttu-id="3f23a-114">Mit dem `<seealso>`-Tag kann der Text angegeben werden, der im Abschnitt „Siehe auch“ angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3f23a-114">The `<seealso>` tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="3f23a-115">Mit [\<see>](./see.md) kann ein Link im Text angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3f23a-115">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="3f23a-116">Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3f23a-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="3f23a-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f23a-117">Example</span></span>

<span data-ttu-id="3f23a-118">Unter [\<summary>](./summary.md) finden Sie ein Beispiel für die Verwendung von \<seealso>.</span><span class="sxs-lookup"><span data-stu-id="3f23a-118">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f23a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f23a-119">See also</span></span>

- [<span data-ttu-id="3f23a-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3f23a-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="3f23a-121">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="3f23a-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
