---
title: -delaysign (C#-Compileroptionen)
ms.date: 05/15/2018
f1_keywords:
- /delaysign
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
ms.openlocfilehash: 9fdc02c22d9d8c8a709155e43a17ebf0d86dfd69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970444"
---
# <a name="-delaysign-c-compiler-options"></a><span data-ttu-id="4bd0a-102">-delaysign (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="4bd0a-102">-delaysign (C# Compiler Options)</span></span>

<span data-ttu-id="4bd0a-103">Durch diese Option reserviert der Compiler Speicherplatz in der Ausgabedatei, damit digitale Signaturen später hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>

## <a name="syntax"></a><span data-ttu-id="4bd0a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bd0a-104">Syntax</span></span>

```console
-delaysign[ + | - ]
```

## <a name="arguments"></a><span data-ttu-id="4bd0a-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="4bd0a-105">Arguments</span></span>

<span data-ttu-id="4bd0a-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="4bd0a-106">`+` &#124; `-`</span></span>

<span data-ttu-id="4bd0a-107">Verwenden Sie **-delaysign-** , wenn die Assembly vollständig signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-107">Use **-delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="4bd0a-108">Verwenden Sie **-delaysign+** , wenn Sie nur den öffentlichen Schlüssel in der Assembly platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-108">Use **-delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="4bd0a-109">Der Standardwert ist **-delaysign-** .</span><span class="sxs-lookup"><span data-stu-id="4bd0a-109">The default is **-delaysign-**.</span></span>

## <a name="remarks"></a><span data-ttu-id="4bd0a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4bd0a-110">Remarks</span></span>

<span data-ttu-id="4bd0a-111">Die Option **-delaysign** hat keine Auswirkung, wenn Sie nicht mit [-keyfile](./keyfile-compiler-option.md) oder [-keycontainer](./keycontainer-compiler-option.md) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-111">The **-delaysign** option has no effect unless used with [-keyfile](./keyfile-compiler-option.md) or [-keycontainer](./keycontainer-compiler-option.md).</span></span>

<span data-ttu-id="4bd0a-112">Die Optionen **-delaysign** und **-publicsign** schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-112">The **-delaysign** and **-publicsign** options are mutually exclusive.</span></span>

<span data-ttu-id="4bd0a-113">Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="4bd0a-114">Dadurch wird eine digitale Signatur erstellt, die in der Datei mit dem Manifest gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-114">That operation creates a digital signature which is stored in the file that contains the manifest.</span></span> <span data-ttu-id="4bd0a-115">Wenn eine Assembly mit Verzögerung signiert wird, wird die Signatur vom Compiler nicht berechnet und gespeichert, sondern lediglich ein Bereich in der Datei reserviert, damit die Signatur zu einem späteren Zeitpunkt hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-115">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>

<span data-ttu-id="4bd0a-116">Mit **-delaysign+** können Tester die Assembly beispielsweise im globalen Cache ablegen.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-116">For example, using **-delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="4bd0a-117">Nach dem Testen können Sie die Assembly vollständig signieren, indem Sie den privaten Schlüssel der Assembly mithilfe des Hilfsprogramms [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) platzieren.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-117">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](../../../framework/tools/al-exe-assembly-linker.md) utility.</span></span>

<span data-ttu-id="4bd0a-118">Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../standard/assembly/create-use-strong-named.md) und [Verzögertes Signieren einer Assembly](../../../standard/assembly/delay-sign.md).</span><span class="sxs-lookup"><span data-stu-id="4bd0a-118">For more information, see [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) and [Delay Signing an Assembly](../../../standard/assembly/delay-sign.md).</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="4bd0a-119">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="4bd0a-119">To set this compiler option in the Visual Studio development environment</span></span>

1. <span data-ttu-id="4bd0a-120">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-120">Open the **Properties** page for the project.</span></span>
1. <span data-ttu-id="4bd0a-121">Bearbeiten Sie die Eigenschaft **Nur verzögerte Signierung**.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-121">Modify the **Delay sign only** property.</span></span>

<span data-ttu-id="4bd0a-122">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="4bd0a-122">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>

## <a name="see-also"></a><span data-ttu-id="4bd0a-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4bd0a-123">See also</span></span>

- [<span data-ttu-id="4bd0a-124">C#-Option -publicsign</span><span class="sxs-lookup"><span data-stu-id="4bd0a-124">C# -publicsign option</span></span>](publicsign-compiler-option.md)
- [<span data-ttu-id="4bd0a-125">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="4bd0a-125">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="4bd0a-126">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="4bd0a-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
