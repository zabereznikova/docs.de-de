---
title: "Gewusst wie: Erstellen eines öffentlichen/privaten Schlüsselpaars"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 772bcae9c3467553e4ca90989a82798155ee034c
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-public-private-key-pair"></a><span data-ttu-id="a05b6-102">Gewusst wie: Erstellen eines öffentlichen/privaten Schlüsselpaars</span><span class="sxs-lookup"><span data-stu-id="a05b6-102">How to: Create a Public-Private Key Pair</span></span>
<span data-ttu-id="a05b6-103">Um eine Assembly mit einem starken Namen zu signieren, benötigen Sie ein Schlüsselpaar, das aus einem öffentlichen und einem privaten Schlüssel besteht.</span><span class="sxs-lookup"><span data-stu-id="a05b6-103">To sign an assembly with a strong name, you must have a public/private key pair.</span></span> <span data-ttu-id="a05b6-104">Dieses kryptografische Schlüsselpaar wird während der Kompilierung zum Erstellen einer Assembly mit starkem Namen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a05b6-104">This public and private cryptographic key pair is used during compilation to create a strong-named assembly.</span></span> <span data-ttu-id="a05b6-105">Sie können ein Schlüsselpaar mit dem [Strong Name-Tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) erstellen.</span><span class="sxs-lookup"><span data-stu-id="a05b6-105">You can create a key pair using the [Strong Name tool (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md).</span></span> <span data-ttu-id="a05b6-106">Schlüsselpaardateien haben in der Regel die Erweiterung SNK.</span><span class="sxs-lookup"><span data-stu-id="a05b6-106">Key pair files usually have an .snk extension.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a05b6-107">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] umfassen die Projekteigenschaftenseiten für C# und Visual Basic die Registerkarte **Signierung**, auf der Sie auswählen können, ob vorhandene Schlüsseldateien verwendet oder neue Schlüsseldateien generiert werden sollen, ohne „Sn.exe“ zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a05b6-107">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], the C# and Visual Basic project property pages include a **Signing** tab that enables you to select existing key files or to generate new key files without using Sn.exe.</span></span> <span data-ttu-id="a05b6-108">In Visual C++ können Sie den Speicherort einer vorhandenen Schlüsseldatei auf der Eigenschaftenseite **Erweitert** im Abschnitt **Linker** des Abschnitts **Konfigurationseigenschaften** im Fenster **Eigenschaftenseiten** angeben.</span><span class="sxs-lookup"><span data-stu-id="a05b6-108">In Visual C++, you can specify the location of an existing key file in the **Advanced** property page in the **Linker** section of the **Configuration Properties** section of the **Property Pages** window.</span></span> <span data-ttu-id="a05b6-109">Die Verwendung des <xref:System.Reflection.AssemblyKeyFileAttribute>-Attributs zur Angabe eines Schlüsseldateipaares gilt ab [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] als veraltet.</span><span class="sxs-lookup"><span data-stu-id="a05b6-109">The use of the <xref:System.Reflection.AssemblyKeyFileAttribute> attribute to identify key file pairs has been made obsolete beginning with [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].</span></span>  
  
### <a name="to-create-a-key-pair"></a><span data-ttu-id="a05b6-110">So erstellen Sie ein Schlüsselpaar</span><span class="sxs-lookup"><span data-stu-id="a05b6-110">To create a key pair</span></span>  
  
1.  <span data-ttu-id="a05b6-111">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="a05b6-111">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="a05b6-112">**sn –k** \<*Dateiname*></span><span class="sxs-lookup"><span data-stu-id="a05b6-112">**sn –k** \<*file name*></span></span>  
  
     <span data-ttu-id="a05b6-113">Bei diesem Befehl bezeichnet *Dateiname* den Namen der Ausgabedatei, die das Schlüsselpaar enthält.</span><span class="sxs-lookup"><span data-stu-id="a05b6-113">In this command, *file name* is the name of the output file containing the key pair.</span></span>  
  
 <span data-ttu-id="a05b6-114">Im folgenden Beispiel wird ein Schlüsselpaar mit dem Namen `sgKey.snk` erstellt.</span><span class="sxs-lookup"><span data-stu-id="a05b6-114">The following example creates a key pair called `sgKey.snk`.</span></span>  
  
```  
sn -k sgKey.snk  
```  
  
 <span data-ttu-id="a05b6-115">Wenn Sie eine Assembly verzögert signieren möchten und beide Schlüssel kontrollieren (was außer in Testszenarien kaum vorkommt), können Sie die folgenden Befehle verwenden, um ein Schlüsselpaar zu generieren, und daraus anschließend den öffentlichen Schlüssel in eine separate Datei extrahieren.</span><span class="sxs-lookup"><span data-stu-id="a05b6-115">If you intend to delay sign an assembly and you control the whole key pair (which is unlikely outside test scenarios), you can use the following commands to generate a key pair and then extract the public key from it into a separate file.</span></span> <span data-ttu-id="a05b6-116">Erstellen Sie zuerst das Schlüsselpaar:</span><span class="sxs-lookup"><span data-stu-id="a05b6-116">First, create the key pair:</span></span>  
  
```  
sn -k keypair.snk  
```  
  
 <span data-ttu-id="a05b6-117">Extrahieren Sie anschließend den öffentlichen Schlüssel aus dem Schlüsselpaar, und kopieren Sie ihn dann in eine separate Datei:</span><span class="sxs-lookup"><span data-stu-id="a05b6-117">Next, extract the public key from the key pair and copy it to a separate file:</span></span>  
  
```  
sn -p keypair.snk public.snk  
```  
  
 <span data-ttu-id="a05b6-118">Nachdem Sie das Schlüsselpaar erstellt haben, müssen Sie die Datei so ablegen, dass die Tools zur Signierung mit starkem Namen Zugriff darauf haben.</span><span class="sxs-lookup"><span data-stu-id="a05b6-118">Once you create the key pair, you must put the file where the strong name signing tools can find it.</span></span>  
  
 <span data-ttu-id="a05b6-119">Beim Signieren einer Assembly mit einem starken Namen sucht das [Assembly Linker-Tool (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) nach der Schlüsseldatei relativ zum aktuellen und zum Ausgabeverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="a05b6-119">When signing an assembly with a strong name, the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) looks for the key file relative to the current directory and to the output directory.</span></span> <span data-ttu-id="a05b6-120">Wenn Sie einen Befehlszeilencompiler verwenden, können Sie den Schlüssel einfach in das aktuelle Verzeichnis kopieren, das die Codemodule enthält.</span><span class="sxs-lookup"><span data-stu-id="a05b6-120">When using command-line compilers, you can simply copy the key to the current directory containing your code modules.</span></span>  
  
 <span data-ttu-id="a05b6-121">Wenn Sie eine frühere Version von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] verwenden, die in den Projekteigenschaften nicht die Registerkarte **Signierung** aufweist, sollten Sie die Schlüsseldatei im Projektverzeichnis speichern und das Dateiattribut wie folgt festlegen:</span><span class="sxs-lookup"><span data-stu-id="a05b6-121">If you are using an earlier version of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] that does not have a **Signing** tab in the project properties, the recommended key file location is the project directory with the file attribute specified as follows:</span></span>  
  
 <span data-ttu-id="a05b6-122">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span><span class="sxs-lookup"><span data-stu-id="a05b6-122">[!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)] [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)] [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a05b6-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a05b6-123">See Also</span></span>  
 [<span data-ttu-id="a05b6-124">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="a05b6-124">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

