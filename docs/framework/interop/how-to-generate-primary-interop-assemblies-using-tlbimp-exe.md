---
title: 'Vorgehensweise: Generieren primärer Interopassemblys mit „Tlbimp.exe“'
description: Erfahren Sie, wie Sie mit dem Type Library Importer-Tool (Tlbimp.exe), das vom Windows SDK bereitgestellt wird, primäre Interopassemblys generieren.
ms.date: 03/30/2017
helpviewer_keywords:
- primary interop assemblies, generating
- Tlbimp.exe
- Type Library Importer
ms.assetid: 5419011c-6e57-40f6-8c65-386db8f7a651
ms.openlocfilehash: 779b4863b6f1513f3566d4ab31660d88cda1039b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619129"
---
# <a name="how-to-generate-primary-interop-assemblies-using-tlbimpexe"></a><span data-ttu-id="0bf6d-103">Vorgehensweise: Generieren primärer Interopassemblys mit „Tlbimp.exe“</span><span class="sxs-lookup"><span data-stu-id="0bf6d-103">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>

<span data-ttu-id="0bf6d-104">Es gibt zwei Möglichkeiten, eine primäre Interop-Assembly zu generieren:</span><span class="sxs-lookup"><span data-stu-id="0bf6d-104">There are two ways to generate a primary interop assembly:</span></span>

- <span data-ttu-id="0bf6d-105">Verwenden von [„Tlbimp.exe“ (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md), das im Windows SDK bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-105">Using the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) provided by the Windows SDK.</span></span>

  <span data-ttu-id="0bf6d-106">Die einfachste Möglichkeit zum Erstellen primärer Interop-Assemblys besteht darin, [Tlbimp.exe (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-106">The most straightforward way to produce primary interop assemblies is to use the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="0bf6d-107">"Tlbimp.exe" bietet die folgenden Schutzvorrichtungen:</span><span class="sxs-lookup"><span data-stu-id="0bf6d-107">Tlbimp.exe provides the following safeguards:</span></span>

  - <span data-ttu-id="0bf6d-108">Es prüft auf andere registrierte primäre Interop-Assemblys, bevor es neue Interop-Assemblys für irgendwelche geschachtelten Typbibliotheksverweise erstellt.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-108">Checks for other registered primary interop assemblies before creating new interop assemblies for any nested type library references.</span></span>

  - <span data-ttu-id="0bf6d-109">Es kann die primäre Interop-Assembly nicht ausgeben, wenn Sie nicht entweder den Container oder den Dateinamen angeben, um der primären Interop-Assembly einen starken Namen zu geben.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-109">Fails to emit the primary interop assembly if you do not specify either the container or file name to give the primary interop assembly a strong name.</span></span>

  - <span data-ttu-id="0bf6d-110">Es kann keine primäre Interop-Assembly ausgeben, wenn Sie keine Verweise auf abhängige Assemblys angeben.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-110">Fails to emit a primary interop assembly if you omit references to dependent assemblies.</span></span>

  - <span data-ttu-id="0bf6d-111">Es kann keine primäre Interop-Assembly ausgeben, wenn Sie Verweise auf abhängige Assemblys hinzufügen, die keine primären Interop-Assemblys sind.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-111">Fails to emit a primary interop assembly if you add references to dependent assemblies that are not primary interop assemblies.</span></span>

- <span data-ttu-id="0bf6d-112">Manuelles Erstellen von primären Interop-Assemblys in Quellcode, indem eine Sprache verwendet wird, die mit der Common Language Specification (CLS) kompatibel ist, beispielsweise C#.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-112">Creating primary interop assemblies manually in source code by using a language that is compliant with the Common Language Specification (CLS), such as C#.</span></span> <span data-ttu-id="0bf6d-113">Dieser Ansatz ist hilfreich, wenn keine Typbibliothek verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-113">This approach is useful when a type library is unavailable.</span></span>

<span data-ttu-id="0bf6d-114">Sie benötigen ein kryptografisches Schlüsselpaar, um eine Assembly mit einem starken Namen zu signieren.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-114">You must have a cryptographic key pair to sign the assembly with a strong name.</span></span> <span data-ttu-id="0bf6d-115">Ausführliche Informationen finden Sie unter [Erstellen eines Schlüsselpaares](../../standard/assembly/create-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="0bf6d-115">For details, see [Creating A Key Pair](../../standard/assembly/create-public-private-key-pair.md).</span></span>

### <a name="to-generate-a-primary-interop-assembly-using-tlbimpexe"></a><span data-ttu-id="0bf6d-116">So generieren Sie eine primäre Interop-Assemblys mit "Tlbimp.exe"</span><span class="sxs-lookup"><span data-stu-id="0bf6d-116">To generate a primary interop assembly using Tlbimp.exe</span></span>

1. <span data-ttu-id="0bf6d-117">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="0bf6d-117">At the command prompt, type:</span></span>

    <span data-ttu-id="0bf6d-118">**tlbimp** *tlbfile*  **/primary /keyfile:** *Dateiname* **/out:** *Assemblyname*</span><span class="sxs-lookup"><span data-stu-id="0bf6d-118">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span></span>

    <span data-ttu-id="0bf6d-119">In diesem Befehl ist *tlbfile* die Datei, die die COM-Typbibliothek enthält, *filename* der Name des Containers oder der Datei, die das Schlüsselpaar enthalten, und *assemblyname* der Name der zu unterzeichnenden Assembly mit einem starken Namen.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-119">In this command, *tlbfile* is the file containing the COM type library, *filename* is the name of the container or file that contains the key pair, and *assemblyname* is the name of the assembly to sign with a strong name.</span></span>

<span data-ttu-id="0bf6d-120">Primäre Interop-Assemblys können nur auf andere primäre Interop-Assemblys verweisen.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-120">Primary interop assemblies can reference only other primary interop assemblies.</span></span> <span data-ttu-id="0bf6d-121">Wenn Ihre Assembly auf Typen aus einer COM-Typbibliothek eines Drittanbieters verweist, müssen Sie eine primäre Interop-Assembly von dem Herausgeber abrufen, bevor Sie Ihre primäre Interop-Assembly generieren können.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-121">If your assembly references types from a third-party COM type library, you must obtain a primary interop assembly from the publisher before you can generate your primary interop assembly.</span></span> <span data-ttu-id="0bf6d-122">Wenn Sie der Herausgeber sind, müssen Sie eine primäre Interop-Assembly für die abhängige Typbibliothek generieren, bevor Sie die verweisende primäre Interop-Assembly generieren.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-122">If you are the publisher, you must generate a primary interop assembly for the dependent type library before generating the referencing primary interop assembly.</span></span>

<span data-ttu-id="0bf6d-123">Eine abhängige primäre Interop-Assembly mit einer Versionsnummer, die von der der ursprünglichen Typbibliothek abweicht, kann nicht erkennt werden, wenn sie im aktuellen Verzeichnis installiert ist.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-123">A dependent primary interop assembly with a version number that differs from that of the original type library is not discoverable when installed in the current directory.</span></span> <span data-ttu-id="0bf6d-124">Sie müssen die abhängige primäre Interop-Assembly in der Windows-Registrierung registrieren oder die **/reference**-Option verwenden, um sicherzustellen, dass „Tlbimp.exe“ die abhängige DLL finden kann.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-124">You must either register the dependent primary interop assembly in the Windows registry or use the **/reference** option to be sure that Tlbimp.exe finds the dependent DLL.</span></span>

<span data-ttu-id="0bf6d-125">Sie können auch mehrere Versionen einer Typbibliothek einschließen.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-125">You can also wrap multiple versions of a type library.</span></span> <span data-ttu-id="0bf6d-126">Anweisungen hierzu finden Sie unter [Vorgehensweise: Einschließen mehrerer Versionen von Typbibliotheken](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="0bf6d-126">For instructions, see [How to: Wrap Multiple Versions of Type Libraries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="0bf6d-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0bf6d-127">Example</span></span>

<span data-ttu-id="0bf6d-128">Im folgenden Beispiel wird die COM-Typbibliothek `LibUtil.tlb` importiert und die Assembly `LibUtil.dll` mit einem starken Namen signiert, indem die Schlüsseldatei `CompanyA.snk` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-128">The following example imports the COM type library `LibUtil.tlb` and signs the assembly `LibUtil.dll` with a strong name using the key file `CompanyA.snk`.</span></span> <span data-ttu-id="0bf6d-129">Dadurch, dass kein spezieller Namespacename angegeben ist, wird in diesem Beispiel wird der Standardnamespace, `LibUtil`, erstellt.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-129">By omitting a specific namespace name, this example produces the default namespace, `LibUtil`.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /out:LibUtil.dll
```

<span data-ttu-id="0bf6d-130">Für einen aussagekräftigeren Namen (mit der Benennungsrichtline *Herstellername*.*Bibliotheksname*) überschreibt das folgende Beispiel den Standardnamen für die Assemblydatei und den Namespace.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-130">For a more descriptive name (using the *VendorName*.*LibraryName* naming guideline), the following example overrides the default assembly file name and namespace name.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /namespace:CompanyA.LibUtil /out:CompanyA.LibUtil.dll
```

<span data-ttu-id="0bf6d-131">Im folgenden Beispiel wird `MyLib.tlb` importiert, in der auf `CompanyA.LibUtil.dll` verwiesen wird, und wird die Assembly `CompanyB.MyLib.dll` über die Schlüsseldatei `CompanyB.snk` mit einem starken Namen signiert.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-131">The following example imports `MyLib.tlb`, which references `CompanyA.LibUtil.dll`, and signs the assembly `CompanyB.MyLib.dll` with a strong name using the key file `CompanyB.snk`.</span></span> <span data-ttu-id="0bf6d-132">Der Namespacename `CompanyB.MyLib` wird verwendet, um den Standardnamespacenamen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="0bf6d-132">The namespace, `CompanyB.MyLib`, overrides the default namespace name.</span></span>

```console
tlbimp MyLib.tlb /primary /keyfile:CompanyB.snk /namespace:CompanyB.MyLib /reference:CompanyA.LibUtil.dll /out:CompanyB.MyLib.dll
```

## <a name="see-also"></a><span data-ttu-id="0bf6d-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bf6d-133">See also</span></span>

- [<span data-ttu-id="0bf6d-134">How to: Registrieren primärer Interopassemblys</span><span class="sxs-lookup"><span data-stu-id="0bf6d-134">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)
