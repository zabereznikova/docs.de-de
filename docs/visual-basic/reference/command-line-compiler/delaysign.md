---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: c9bb302e2b34ebe1f51cf39bb3db1094d420d7f4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408698"
---
# <a name="-delaysign"></a><span data-ttu-id="a0741-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="a0741-102">-delaysign</span></span>

<span data-ttu-id="a0741-103">Gibt an, ob die Assembly vollständig oder teilweise signiert wird.</span><span class="sxs-lookup"><span data-stu-id="a0741-103">Specifies whether the assembly will be fully or partially signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="a0741-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0741-104">Syntax</span></span>

```console
-delaysign[+ | -]
```

## <a name="arguments"></a><span data-ttu-id="a0741-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="a0741-105">Arguments</span></span>

<span data-ttu-id="a0741-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a0741-106">`+` &#124; `-`</span></span>  
<span data-ttu-id="a0741-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="a0741-107">Optional.</span></span> <span data-ttu-id="a0741-108">Verwenden Sie `-delaysign-`, wenn die Assembly vollständig signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a0741-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="a0741-109">Verwenden Sie `-delaysign+`, wenn Sie den öffentlichen Schlüssel in der Assembly platzieren und Speicherplatz für den signierten Hash reservieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a0741-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="a0741-110">Der Standardwert ist `-delaysign-`.</span><span class="sxs-lookup"><span data-stu-id="a0741-110">The default is `-delaysign-`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a0741-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0741-111">Remarks</span></span>

<span data-ttu-id="a0741-112">Die Option `-delaysign` hat keine Auswirkung, wenn Sie nicht mit [-keyfile](keyfile.md) oder [-keycontainer](keycontainer.md) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a0741-112">The `-delaysign` option has no effect unless used with [-keyfile](keyfile.md) or [-keycontainer](keycontainer.md).</span></span>

<span data-ttu-id="a0741-113">Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="a0741-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="a0741-114">Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a0741-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="a0741-115">Wenn eine Assembly mit Verzögerung signiert wird, wird die Signatur vom Compiler nicht berechnet und gespeichert, sondern lediglich ein Bereich in der Datei reserviert, damit die Signatur zu einem späteren Zeitpunkt hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a0741-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="a0741-116">Beispielsweise kann ein Entwickler in einer Organisation mithilfe von `-delaysign+` nicht signierte Testversionen einer Assembly verteilen, die Tester mit dem globalen Assemblycache registrieren und verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a0741-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="a0741-117">Wenn die Arbeit an der Assembly abgeschlossen ist, kann die Person, die für den privaten Schlüssel der Organisation zuständig ist, die Assembly vollständig signieren.</span><span class="sxs-lookup"><span data-stu-id="a0741-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="a0741-118">Diese Trennung schützt den privaten Schlüssel der Organisation vor der Offenlegung und ermöglicht es allen Entwicklern, an den Assemblys zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a0741-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>

<span data-ttu-id="a0741-119">Weitere Informationen zum Signieren von Assemblys finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../standard/assembly/create-use-strong-named.md).</span><span class="sxs-lookup"><span data-stu-id="a0741-119">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>

### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="a0741-120">So legen Sie -delaysign in der Visual Studio-IDE fest</span><span class="sxs-lookup"><span data-stu-id="a0741-120">To set -delaysign in the Visual Studio integrated development environment</span></span>

1. <span data-ttu-id="a0741-121">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="a0741-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a0741-122">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a0741-122">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="a0741-123">Klicken Sie auf die Registerkarte **Signierung**.</span><span class="sxs-lookup"><span data-stu-id="a0741-123">Click the **Signing** tab.</span></span>

3. <span data-ttu-id="a0741-124">Legen Sie den Wert im Feld **Nur verzögerte Signierung** fest.</span><span class="sxs-lookup"><span data-stu-id="a0741-124">Set the value in the **Delay sign only** box.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0741-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0741-125">See also</span></span>

- [<span data-ttu-id="a0741-126">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="a0741-126">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="a0741-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="a0741-127">-keyfile</span></span>](keyfile.md)
- [<span data-ttu-id="a0741-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="a0741-128">-keycontainer</span></span>](keycontainer.md)
- [<span data-ttu-id="a0741-129">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="a0741-129">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
