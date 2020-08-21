---
title: -publicsign (C#-Compileroptionen)
ms.date: 05/15/2018
f1_keywords:
- /publicsign
helpviewer_keywords:
- -publicsign compiler option [C#]
- publicsign compiler option [C#]
- /publicsign compiler option [C#]
ms.openlocfilehash: 2655e0216a412053e052ab2ec2fcc8c68ea4f968
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88268048"
---
# <a name="-publicsign-c-compiler-options"></a><span data-ttu-id="26451-102">-publicsign (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="26451-102">-publicsign (C# Compiler Options)</span></span>

<span data-ttu-id="26451-103">Diese Option bewirkt, dass der Compiler einen öffentlichen Schlüssel anwendet, die Assembly aber tatsächlich nicht signiert.</span><span class="sxs-lookup"><span data-stu-id="26451-103">This option causes the compiler to apply a public key but does not actually sign the assembly.</span></span> <span data-ttu-id="26451-104">Mit der Option **-publicsign** wird zudem ein Bit in der Assembly festgelegt, das der Runtime mitteilt, dass die Datei tatsächlich signiert wurde.</span><span class="sxs-lookup"><span data-stu-id="26451-104">The **-publicsign** option also sets a bit in the assembly that tells the runtime that the file is actually signed.</span></span>

## <a name="syntax"></a><span data-ttu-id="26451-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="26451-105">Syntax</span></span>

```console
-publicsign
```

## <a name="arguments"></a><span data-ttu-id="26451-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="26451-106">Arguments</span></span>

<span data-ttu-id="26451-107">Keine.</span><span class="sxs-lookup"><span data-stu-id="26451-107">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="26451-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="26451-108">Remarks</span></span>

<span data-ttu-id="26451-109">Für die Option **-publicsign** müssen die Optionen [-keyfile](keyfile-compiler-option.md) oder [-keycontainer](keycontainer-compiler-option.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="26451-109">The **-publicsign** option requires the use of the [-keyfile](keyfile-compiler-option.md) or [-keycontainer](keycontainer-compiler-option.md).</span></span> <span data-ttu-id="26451-110">Die Optionen **keyfile** oder **keycontainer** geben den öffentlichen Schlüssel an.</span><span class="sxs-lookup"><span data-stu-id="26451-110">The **keyfile** or **keycontainer** options specify the public key.</span></span>

<span data-ttu-id="26451-111">Die Optionen **-delaysign** und **-publicsign** schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="26451-111">The **-publicsign** and **-delaysign** options are mutually exclusive.</span></span>

<span data-ttu-id="26451-112">Bei der öffentlichen Signierung, die manchmal auch als „Fake-Signierung“ oder „OSS-Signierung“ bezeichnet wird, wird der öffentliche Schlüssel in eine Ausgabeassembly eingefügt und das Flag „signed“ (signiert) festgelegt. Die Assembly wird jedoch nicht wirklich mit einem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="26451-112">Sometimes called "fake sign" or "OSS sign", public signing includes the public key in an output assembly and sets the "signed" flag, but doesn't actually sign the assembly with a private key.</span></span> <span data-ttu-id="26451-113">Dies ist bei Open Source-Projekten hilfreich, bei denen Personen Assemblys erstellen möchten, die mit den veröffentlichten, „vollständig signierten“ Assemblys kompatibel sind, jedoch keinen Zugriff auf den privaten Schlüssel zum Signieren der Assemblys haben.</span><span class="sxs-lookup"><span data-stu-id="26451-113">This is useful for open source projects where people want to build assemblies which are compatible with the released "fully signed" assemblies, but don't have access to the private key used to sign the assemblies.</span></span> <span data-ttu-id="26451-114">Da fast keine Benutzer tatsächlich überprüfen müssen, ob die Assembly vollständig signiert ist, können diese öffentlich erstellten Assemblys in fast jedem Szenario eingesetzt werden, in denen die vollständig signierte Assembly verwendet werden würde.</span><span class="sxs-lookup"><span data-stu-id="26451-114">Since almost no consumers actually need to check if the assembly is fully signed, these publicly built assemblies are useable in almost every scenario where the fully signed one would be used.</span></span>

### <a name="to-set-this-compiler-option-in-a-csproj-file"></a><span data-ttu-id="26451-115">Festlegen dieser Compileroption in einer CSPROJ-Datei</span><span class="sxs-lookup"><span data-stu-id="26451-115">To set this compiler option in a csproj file</span></span>

<span data-ttu-id="26451-116">Öffnen Sie die CSPROJ-Datei für ein Projekt, und fügen Sie das folgende Element hinzu:</span><span class="sxs-lookup"><span data-stu-id="26451-116">Open the .csproj file for a project, and add the following element:</span></span>

```xml
<PublicSign>true</PublicSign>
```

## <a name="see-also"></a><span data-ttu-id="26451-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26451-117">See also</span></span>

- [<span data-ttu-id="26451-118">C#-Compileroption „-delaysign“</span><span class="sxs-lookup"><span data-stu-id="26451-118">C# Compiler -delaysign option</span></span>](delaysign-compiler-option.md)
- [<span data-ttu-id="26451-119">C#-Compileroption „-keyfile“</span><span class="sxs-lookup"><span data-stu-id="26451-119">C# Compiler -keyfile option</span></span>](keyfile-compiler-option.md)
- [<span data-ttu-id="26451-120">C#-Compileroption „-keycontainer“</span><span class="sxs-lookup"><span data-stu-id="26451-120">C# Compiler -keycontainer option</span></span>](keycontainer-compiler-option.md)
- [<span data-ttu-id="26451-121">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="26451-121">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="26451-122">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="26451-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
