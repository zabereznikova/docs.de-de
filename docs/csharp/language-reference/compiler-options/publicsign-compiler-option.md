---
description: -publicsign (C#-Compileroptionen)
title: -publicsign (C#-Compileroptionen)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 525912c7f50aa6b51e602be7b9258f1f5907daac
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124811"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="a538d-103">-publicsign (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a538d-103">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="a538d-104">Diese Option bewirkt, dass der Compiler einen öffentlichen Schlüssel anwendet, die Assembly aber tatsächlich nicht signiert.</span><span class="sxs-lookup"><span data-stu-id="a538d-104">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="a538d-105">Mit der Option **-publicsign** wird zudem ein Bit in der Assembly festgelegt, das der Runtime mitteilt, dass die Datei tatsächlich signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a538d-105">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="a538d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a538d-106">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="a538d-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="a538d-107">Arguments</span></span>

<span data-ttu-id="a538d-108">Keine.</span><span class="sxs-lookup"><span data-stu-id="a538d-108">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="a538d-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a538d-109">Remarks</span></span>

<span data-ttu-id="a538d-110">Für die Option **-publicsign** müssen die Optionen [-keyfile](keyfile-compiler-option.md) oder [-keycontainer](keycontainer-compiler-option.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a538d-110">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="a538d-111">Die Optionen **keyfile** oder **keycontainer** geben den öffentlichen Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="a538d-111">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="a538d-112">Die Optionen **-delaysign** und **-publicsign** schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="a538d-112">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="a538d-113">Bei der öffentlichen Signierung, die manchmal auch als „Fake-Signierung“ oder „OSS-Signierung“ bezeichnet wird, wird der öffentliche Schlüssel in eine Ausgabeassembly eingefügt und das Flag „signed“ (signiert) festgelegt. Die Assembly wird jedoch nicht wirklich mit einem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="a538d-113">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="a538d-114">Dies ist bei Open Source-Projekten hilfreich, bei denen Personen Assemblys erstellen möchten, die mit den veröffentlichten, „vollständig signierten“ Assemblys kompatibel sind, jedoch keinen Zugriff auf den privaten Schlüssel zum Signieren der Assemblys haben.</span><span class="sxs-lookup"><span data-stu-id="a538d-114">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="a538d-115">Da fast keine Benutzer tatsächlich überprüfen müssen, ob die Assembly vollständig signiert ist, können diese öffentlich erstellten Assemblys in fast jedem Szenario eingesetzt werden, in denen die vollständig signierte Assembly verwendet werden würde.</span><span class="sxs-lookup"><span data-stu-id="a538d-115">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a><span data-ttu-id="a538d-116">Festlegen dieser Compileroption in einer CSPROJ-Datei</span><span class="sxs-lookup"><span data-stu-id="a538d-116">To set this compiler option in a csproj file</span></span>

<span data-ttu-id="a538d-117">Öffnen Sie die CSPROJ-Datei für ein Projekt, und fügen Sie das folgende Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="a538d-117">Open the .csproj file for a project, and add the following element:</span></span>

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a><span data-ttu-id="a538d-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a538d-118">See also</span></span>

- [<span data-ttu-id="a538d-119">C#-Compileroption „-delaysign“</span><span class="sxs-lookup"><span data-stu-id="a538d-119">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)
- [<span data-ttu-id="a538d-120">C#-Compileroption „-keyfile“</span><span class="sxs-lookup"><span data-stu-id="a538d-120">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="a538d-121">C#-Compileroption „-keycontainer“</span><span class="sxs-lookup"><span data-stu-id="a538d-121">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)
- [<span data-ttu-id="a538d-122">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="a538d-122">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="a538d-123">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="a538d-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
