---
title: 'Vorgehensweise: Generieren primärer Interopassemblys mit „Tlbimp.exe“'
ms.date: 03/30/2017
helpviewer_keywords:
- primary interop assemblies, generating
- Tlbimp.exe
- Type Library Importer
ms.assetid: 5419011c-6e57-40f6-8c65-386db8f7a651
ms.openlocfilehash: e46295b89b042452cb6e303302a8b88d68d58426
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123908"
---
# <a name="how-to-generate-primary-interop-assemblies-using-tlbimpexe"></a><span data-ttu-id="d9d27-102">Vorgehensweise: Generieren primärer Interopassemblys mit „Tlbimp.exe“</span><span class="sxs-lookup"><span data-stu-id="d9d27-102">How to: Generate Primary Interop Assemblies Using Tlbimp.exe</span></span>

<span data-ttu-id="d9d27-103">Es gibt zwei Möglichkeiten, eine primäre Interop-Assembly zu generieren:</span><span class="sxs-lookup"><span data-stu-id="d9d27-103">There are two ways to generate a primary interop assembly:</span></span>

- <span data-ttu-id="d9d27-104">Verwenden von [„Tlbimp.exe“ (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md), das im Windows SDK bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d9d27-104">Using the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) provided by the Windows SDK.</span></span>

  <span data-ttu-id="d9d27-105">Die einfachste Möglichkeit zum Erstellen primärer Interop-Assemblys besteht darin, [Tlbimp.exe (Type Library Importer-Tool)](../tools/tlbimp-exe-type-library-importer.md) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9d27-105">The most straightforward way to produce primary interop assemblies is to use the [Tlbimp.exe (Type Library Importer)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="d9d27-106">"Tlbimp.exe" bietet die folgenden Schutzvorrichtungen:</span><span class="sxs-lookup"><span data-stu-id="d9d27-106">Tlbimp.exe provides the following safeguards:</span></span>

  - <span data-ttu-id="d9d27-107">Es prüft auf andere registrierte primäre Interop-Assemblys, bevor es neue Interop-Assemblys für irgendwelche geschachtelten Typbibliotheksverweise erstellt.</span><span class="sxs-lookup"><span data-stu-id="d9d27-107">Checks for other registered primary interop assemblies before creating new interop assemblies for any nested type library references.</span></span>

  - <span data-ttu-id="d9d27-108">Es kann die primäre Interop-Assembly nicht ausgeben, wenn Sie nicht entweder den Container oder den Dateinamen angeben, um der primären Interop-Assembly einen starken Namen zu geben.</span><span class="sxs-lookup"><span data-stu-id="d9d27-108">Fails to emit the primary interop assembly if you do not specify either the container or file name to give the primary interop assembly a strong name.</span></span>

  - <span data-ttu-id="d9d27-109">Es kann keine primäre Interop-Assembly ausgeben, wenn Sie keine Verweise auf abhängige Assemblys angeben.</span><span class="sxs-lookup"><span data-stu-id="d9d27-109">Fails to emit a primary interop assembly if you omit references to dependent assemblies.</span></span>

  - <span data-ttu-id="d9d27-110">Es kann keine primäre Interop-Assembly ausgeben, wenn Sie Verweise auf abhängige Assemblys hinzufügen, die keine primären Interop-Assemblys sind.</span><span class="sxs-lookup"><span data-stu-id="d9d27-110">Fails to emit a primary interop assembly if you add references to dependent assemblies that are not primary interop assemblies.</span></span>

- <span data-ttu-id="d9d27-111">Manuelles Erstellen von primären Interop-Assemblys in Quellcode, indem eine Sprache verwendet wird, die mit der Common Language Specification (CLS) kompatibel ist, beispielsweise C#.</span><span class="sxs-lookup"><span data-stu-id="d9d27-111">Creating primary interop assemblies manually in source code by using a language that is compliant with the Common Language Specification (CLS), such as C#.</span></span> <span data-ttu-id="d9d27-112">Dieser Ansatz ist hilfreich, wenn keine Typbibliothek verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d9d27-112">This approach is useful when a type library is unavailable.</span></span>

<span data-ttu-id="d9d27-113">Sie benötigen ein kryptografisches Schlüsselpaar, um eine Assembly mit einem starken Namen zu signieren.</span><span class="sxs-lookup"><span data-stu-id="d9d27-113">You must have a cryptographic key pair to sign the assembly with a strong name.</span></span> <span data-ttu-id="d9d27-114">Ausführliche Informationen finden Sie unter [Erstellen eines Schlüsselpaares](../../standard/assembly/create-public-private-key-pair.md).</span><span class="sxs-lookup"><span data-stu-id="d9d27-114">For details, see [Creating A Key Pair](../../standard/assembly/create-public-private-key-pair.md).</span></span>

### <a name="to-generate-a-primary-interop-assembly-using-tlbimpexe"></a><span data-ttu-id="d9d27-115">So generieren Sie eine primäre Interop-Assemblys mit "Tlbimp.exe"</span><span class="sxs-lookup"><span data-stu-id="d9d27-115">To generate a primary interop assembly using Tlbimp.exe</span></span>

1. <span data-ttu-id="d9d27-116">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d9d27-116">At the command prompt, type:</span></span>

    <span data-ttu-id="d9d27-117">**tlbimp** *tlbfile*  **/primary /keyfile:** *Dateiname* **/out:** *Assemblyname*</span><span class="sxs-lookup"><span data-stu-id="d9d27-117">**tlbimp** *tlbfile*  **/primary /keyfile:** *filename* **/out:** *assemblyname*</span></span>

    <span data-ttu-id="d9d27-118">In diesem Befehl ist *tlbfile* die Datei, die die COM-Typbibliothek enthält, *filename* der Name des Containers oder der Datei, die das Schlüsselpaar enthalten, und *assemblyname* der Name der zu unterzeichnenden Assembly mit einem starken Namen.</span><span class="sxs-lookup"><span data-stu-id="d9d27-118">In this command, *tlbfile* is the file containing the COM type library, *filename* is the name of the container or file that contains the key pair, and *assemblyname* is the name of the assembly to sign with a strong name.</span></span>

<span data-ttu-id="d9d27-119">Primäre Interop-Assemblys können nur auf andere primäre Interop-Assemblys verweisen.</span><span class="sxs-lookup"><span data-stu-id="d9d27-119">Primary interop assemblies can reference only other primary interop assemblies.</span></span> <span data-ttu-id="d9d27-120">Wenn Ihre Assembly auf Typen aus einer COM-Typbibliothek eines Drittanbieters verweist, müssen Sie eine primäre Interop-Assembly von dem Herausgeber abrufen, bevor Sie Ihre primäre Interop-Assembly generieren können.</span><span class="sxs-lookup"><span data-stu-id="d9d27-120">If your assembly references types from a third-party COM type library, you must obtain a primary interop assembly from the publisher before you can generate your primary interop assembly.</span></span> <span data-ttu-id="d9d27-121">Wenn Sie der Herausgeber sind, müssen Sie eine primäre Interop-Assembly für die abhängige Typbibliothek generieren, bevor Sie die verweisende primäre Interop-Assembly generieren.</span><span class="sxs-lookup"><span data-stu-id="d9d27-121">If you are the publisher, you must generate a primary interop assembly for the dependent type library before generating the referencing primary interop assembly.</span></span>

<span data-ttu-id="d9d27-122">Eine abhängige primäre Interop-Assembly mit einer Versionsnummer, die von der der ursprünglichen Typbibliothek abweicht, kann nicht erkennt werden, wenn sie im aktuellen Verzeichnis installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d9d27-122">A dependent primary interop assembly with a version number that differs from that of the original type library is not discoverable when installed in the current directory.</span></span> <span data-ttu-id="d9d27-123">Sie müssen die abhängige primäre Interop-Assembly in der Windows-Registrierung registrieren oder die **/reference**-Option verwenden, um sicherzustellen, dass „Tlbimp.exe“ die abhängige DLL finden kann.</span><span class="sxs-lookup"><span data-stu-id="d9d27-123">You must either register the dependent primary interop assembly in the Windows registry or use the **/reference** option to be sure that Tlbimp.exe finds the dependent DLL.</span></span>

<span data-ttu-id="d9d27-124">Sie können auch mehrere Versionen einer Typbibliothek einschließen.</span><span class="sxs-lookup"><span data-stu-id="d9d27-124">You can also wrap multiple versions of a type library.</span></span> <span data-ttu-id="d9d27-125">Anweisungen hierzu finden Sie unter [Vorgehensweise: Einschließen mehrerer Versionen von Typbibliotheken](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d9d27-125">For instructions, see [How to: Wrap Multiple Versions of Type Libraries](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/1565h6hc(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="d9d27-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d9d27-126">Example</span></span>

<span data-ttu-id="d9d27-127">Im folgenden Beispiel wird die COM-Typbibliothek `LibUtil.tlb` importiert und die Assembly `LibUtil.dll` mit einem starken Namen signiert, indem die Schlüsseldatei `CompanyA.snk` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9d27-127">The following example imports the COM type library `LibUtil.tlb` and signs the assembly `LibUtil.dll` with a strong name using the key file `CompanyA.snk`.</span></span> <span data-ttu-id="d9d27-128">Dadurch, dass kein spezieller Namespacename angegeben ist, wird in diesem Beispiel wird der Standardnamespace, `LibUtil`, erstellt.</span><span class="sxs-lookup"><span data-stu-id="d9d27-128">By omitting a specific namespace name, this example produces the default namespace, `LibUtil`.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /out:LibUtil.dll
```

<span data-ttu-id="d9d27-129">Für einen aussagekräftigeren Namen (mit der Benennungsrichtline *Herstellername*.*Bibliotheksname*) überschreibt das folgende Beispiel den Standardnamen für die Assemblydatei und den Namespace.</span><span class="sxs-lookup"><span data-stu-id="d9d27-129">For a more descriptive name (using the *VendorName*.*LibraryName* naming guideline), the following example overrides the default assembly file name and namespace name.</span></span>

```console
tlbimp LibUtil.tlb /primary /keyfile:CompanyA.snk /namespace:CompanyA.LibUtil /out:CompanyA.LibUtil.dll
```

<span data-ttu-id="d9d27-130">Im folgenden Beispiel wird `MyLib.tlb` importiert, in der auf `CompanyA.LibUtil.dll` verwiesen wird, und wird die Assembly `CompanyB.MyLib.dll` über die Schlüsseldatei `CompanyB.snk` mit einem starken Namen signiert.</span><span class="sxs-lookup"><span data-stu-id="d9d27-130">The following example imports `MyLib.tlb`, which references `CompanyA.LibUtil.dll`, and signs the assembly `CompanyB.MyLib.dll` with a strong name using the key file `CompanyB.snk`.</span></span> <span data-ttu-id="d9d27-131">Der Namespacename `CompanyB.MyLib` wird verwendet, um den Standardnamespacenamen zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="d9d27-131">The namespace, `CompanyB.MyLib`, overrides the default namespace name.</span></span>

```console
tlbimp MyLib.tlb /primary /keyfile:CompanyB.snk /namespace:CompanyB.MyLib /reference:CompanyA.LibUtil.dll /out:CompanyB.MyLib.dll
```

## <a name="see-also"></a><span data-ttu-id="d9d27-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9d27-132">See also</span></span>

- [<span data-ttu-id="d9d27-133">How to: Registrieren primärer Interopassemblys</span><span class="sxs-lookup"><span data-stu-id="d9d27-133">How to: Register Primary Interop Assemblies</span></span>](how-to-register-primary-interop-assemblies.md)
