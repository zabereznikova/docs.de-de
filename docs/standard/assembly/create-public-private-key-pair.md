---
title: 'Vorgehensweise: Erstellen eines Schlüsselpaars aus öffentlichem und privatem Schlüssel'
ms.date: 08/20/2019
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 8a9845e3cd18ff86ec04216ad0e9c5606186b113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73122521"
---
# <a name="how-to-create-a-public-private-key-pair"></a><span data-ttu-id="641fc-102">Vorgehensweise: Erstellen eines Schlüsselpaars aus öffentlichem und privatem Schlüssel</span><span class="sxs-lookup"><span data-stu-id="641fc-102">How to: Create a public-private key pair</span></span>

<span data-ttu-id="641fc-103">Um eine Assembly mit einem starken Namen zu signieren, benötigen Sie ein Schlüsselpaar, das aus einem öffentlichen und einem privaten Schlüssel besteht.</span><span class="sxs-lookup"><span data-stu-id="641fc-103">To sign an assembly with a strong name, you must have a public/private key pair.</span></span> <span data-ttu-id="641fc-104">Dieses kryptografische Schlüsselpaar wird während der Kompilierung zum Erstellen einer Assembly mit starkem Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="641fc-104">This public and private cryptographic key pair is used during compilation to create a strong-named assembly.</span></span> <span data-ttu-id="641fc-105">Sie können ein Schlüsselpaar mit dem [Strong Name-Tool (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="641fc-105">You can create a key pair using the [Strong Name tool (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md).</span></span> <span data-ttu-id="641fc-106">Schlüsselpaardateien haben in der Regel die Erweiterung *SNK*.</span><span class="sxs-lookup"><span data-stu-id="641fc-106">Key pair files usually have an *.snk* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="641fc-107">In Visual Studio umfassen die Projekteigenschaftenseiten für C# und Visual Basic die Registerkarte **Signierung**, auf der Sie auswählen können, ob vorhandene Schlüsseldateien verwendet oder neue Schlüsseldateien generiert werden sollen, ohne dass *Sn.exe* eingesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="641fc-107">In Visual Studio, the C# and Visual Basic project property pages include a **Signing** tab that enables you to select existing key files or to generate new key files without using *Sn.exe*.</span></span> <span data-ttu-id="641fc-108">In Visual C++ können Sie den Speicherort einer vorhandenen Schlüsseldatei auf der Eigenschaftenseite **Erweitert** im Abschnitt **Linker** des Abschnitts **Konfigurationseigenschaften** im Fenster **Eigenschaftenseiten** angeben.</span><span class="sxs-lookup"><span data-stu-id="641fc-108">In Visual C++, you can specify the location of an existing key file in the **Advanced** property page in the **Linker** section of the **Configuration Properties** section of the **Property Pages** window.</span></span> <span data-ttu-id="641fc-109">Die Verwendung des <xref:System.Reflection.AssemblyKeyFileAttribute>-Attributs zur Angabe von Schlüsseldateipaaren ist ab Visual Studio 2005 veraltet.</span><span class="sxs-lookup"><span data-stu-id="641fc-109">The use of the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute to identify key file pairs was made obsolete beginning with Visual Studio 2005.</span></span>

## <a name="create-a-key-pair"></a><span data-ttu-id="641fc-110">Erstellen eines Schlüsselpaars</span><span class="sxs-lookup"><span data-stu-id="641fc-110">Create a key pair</span></span>

<span data-ttu-id="641fc-111">Geben Sie über eine Eingabeaufforderung den folgenden Befehl ein, um ein Schlüsselpaar zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="641fc-111">To create a key pair, at a command prompt, type the following command:</span></span>

<span data-ttu-id="641fc-112">**sn –k** \<*Dateiname*></span><span class="sxs-lookup"><span data-stu-id="641fc-112">**sn –k** \<*file name*></span></span>

<span data-ttu-id="641fc-113">Bei diesem Befehl bezeichnet *Dateiname* den Namen der Ausgabedatei, die das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="641fc-113">In this command, *file name* is the name of the output file containing the key pair.</span></span>

<span data-ttu-id="641fc-114">Im folgenden Beispiel wird ein Schlüsselpaar mit dem Namen *sgKey.snk* erstellt.</span><span class="sxs-lookup"><span data-stu-id="641fc-114">The following example creates a key pair called *sgKey.snk*.</span></span>

```cmd
sn -k sgKey.snk
```

<span data-ttu-id="641fc-115">Wenn Sie eine Assembly verzögert signieren möchten und beide Schlüssel kontrollieren (was außer in Testszenarien kaum vorkommt), können Sie die folgenden Befehle verwenden, um ein Schlüsselpaar zu generieren, und daraus anschließend den öffentlichen Schlüssel in eine separate Datei extrahieren.</span><span class="sxs-lookup"><span data-stu-id="641fc-115">If you intend to delay sign an assembly and you control the whole key pair (which is unlikely outside test scenarios), you can use the following commands to generate a key pair and then extract the public key from it into a separate file.</span></span> <span data-ttu-id="641fc-116">Erstellen Sie zuerst das Schlüsselpaar:</span><span class="sxs-lookup"><span data-stu-id="641fc-116">First, create the key pair:</span></span>

```cmd
sn -k keypair.snk
```

<span data-ttu-id="641fc-117">Extrahieren Sie anschließend den öffentlichen Schlüssel aus dem Schlüsselpaar, und kopieren Sie ihn dann in eine separate Datei:</span><span class="sxs-lookup"><span data-stu-id="641fc-117">Next, extract the public key from the key pair and copy it to a separate file:</span></span>

```cmd
sn -p keypair.snk public.snk
```

<span data-ttu-id="641fc-118">Nachdem Sie das Schlüsselpaar erstellt haben, müssen Sie die Datei so ablegen, dass die Tools zur Signierung mit starkem Namen Zugriff darauf haben.</span><span class="sxs-lookup"><span data-stu-id="641fc-118">Once you create the key pair, you must put the file where the strong name signing tools can find it.</span></span>

<span data-ttu-id="641fc-119">Beim Signieren einer Assembly mit einem starken Namen sucht das [Assembly Linker-Tool (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) nach der Schlüsseldatei relativ zum aktuellen und zum Ausgabeverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="641fc-119">When signing an assembly with a strong name, the [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) looks for the key file relative to the current directory and to the output directory.</span></span> <span data-ttu-id="641fc-120">Wenn Sie einen Befehlszeilencompiler verwenden, können Sie den Schlüssel einfach in das aktuelle Verzeichnis kopieren, das die Codemodule enthält.</span><span class="sxs-lookup"><span data-stu-id="641fc-120">When using command-line compilers, you can simply copy the key to the current directory containing your code modules.</span></span>

<span data-ttu-id="641fc-121">Wenn Sie eine frühere Version von Visual Studio verwenden, die in den Projekteigenschaften nicht die Registerkarte **Signierung** aufweist, sollten Sie die Schlüsseldatei im Projektverzeichnis speichern und das Dateiattribut wie folgt festlegen:</span><span class="sxs-lookup"><span data-stu-id="641fc-121">If you are using an earlier version of Visual Studio that does not have a **Signing** tab in the project properties, the recommended key file location is the project directory with the file attribute specified as follows:</span></span>

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

## <a name="see-also"></a><span data-ttu-id="641fc-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="641fc-122">See also</span></span>

- [<span data-ttu-id="641fc-123">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="641fc-123">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
