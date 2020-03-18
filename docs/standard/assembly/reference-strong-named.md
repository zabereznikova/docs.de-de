---
title: 'Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen'
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: adda4ed2ab5c59e3518b8e724044529a79840ad0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156477"
---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="51d0c-102">Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="51d0c-102">How to: Reference a strong-named assembly</span></span>
<span data-ttu-id="51d0c-103">Beim Verweisen auf Typen oder Ressourcen in einer Assembly mit starkem Namen handelt es sich in der Regel um einen transparenten Prozess.</span><span class="sxs-lookup"><span data-stu-id="51d0c-103">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="51d0c-104">Sie können den Verweis zur Kompilierzeit (frühes Binden) oder zur Runtime vornehmen.</span><span class="sxs-lookup"><span data-stu-id="51d0c-104">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
<span data-ttu-id="51d0c-105">Ein Verweis zur Kompilierzeit tritt auf, wenn Sie den Compiler darauf hinweisen, dass die Assembly, die kompiliert werden soll, explizit auf eine andere Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="51d0c-105">A compile-time reference occurs when you indicate to the compiler that the assembly to be compiled explicitly references another assembly.</span></span> <span data-ttu-id="51d0c-106">Beim Verweisen zur Kompilierzeit ruft der Compiler automatisch den öffentlichen Schlüssel der Zielassembly mit starkem Namen ab und platziert ihn in der Assemblyreferenz der Assembly, die aktuell kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="51d0c-106">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="51d0c-107">Eine Assembly mit starkem Namen kann nur Typen aus anderen Assemblys mit starkem Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="51d0c-107">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="51d0c-108">Andernfalls ist die Sicherheit der Assembly mit starkem Namen beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="51d0c-108">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="51d0c-109">Verweisen auf eine Assembly mit starkem Namen zur Kompilierzeit</span><span class="sxs-lookup"><span data-stu-id="51d0c-109">Make a compile-time reference to a strong-named assembly</span></span>  

<span data-ttu-id="51d0c-110">Geben Sie an einer Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="51d0c-110">At a command prompt, type the following command:</span></span>  

<span data-ttu-id="51d0c-111">\<*Compilerbefehl*>  **/reference:** \<*Assemblyname*></span><span class="sxs-lookup"><span data-stu-id="51d0c-111">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  

<span data-ttu-id="51d0c-112">In diesem Befehl ist der *Compilerbefehl* der Befehl für die Sprache, die Sie verwenden, und *Assemblyname* ist der Name der Assembly mit starkem Namen, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="51d0c-112">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="51d0c-113">Sie können auch andere Compileroptionen verwenden, z.B. die Option **/t:library** zum Erstellen einer Bibliothekassembly.</span><span class="sxs-lookup"><span data-stu-id="51d0c-113">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  

<span data-ttu-id="51d0c-114">Im folgenden Beispiel wird die Assembly *myAssembly.dll* erstellt, die auf die Assembly mit dem starkem Namen *myLibAssembly.dll* aus dem Codemodul *myAssembly.cs* verweist.</span><span class="sxs-lookup"><span data-stu-id="51d0c-114">The following example creates an assembly called *myAssembly.dll* that references a strong-named assembly called *myLibAssembly.dll* from a code module called *myAssembly.cs*.</span></span>  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="51d0c-115">Verweisen auf eine Assembly mit starkem Namen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="51d0c-115">Make a run-time reference to a strong-named assembly</span></span>  
  
<span data-ttu-id="51d0c-116">Wenn Sie zur Laufzeit auf eine Assembly mit starkem Namen verweisen (z. B. mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>- oder <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>-Methode), müssen Sie den Anzeigenamen der Assembly mit starkem Namen verwenden, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="51d0c-116">When you make a run-time reference to a strong-named assembly, for example by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> method, you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="51d0c-117">Die Syntax eines Anzeigenamens lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="51d0c-117">The syntax of a display name is as follows:</span></span>  

<span data-ttu-id="51d0c-118">\<*Assemblyname*> **,** \<*Versionsnummer*> **,** \<*Kultur*> **,** \<*Token des öffentlichen Schlüssels*></span><span class="sxs-lookup"><span data-stu-id="51d0c-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  

<span data-ttu-id="51d0c-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="51d0c-119">For example:</span></span>  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

<span data-ttu-id="51d0c-120">In diesem Beispiel ist `PublicKeyToken` die hexadezimale Form des öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="51d0c-120">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="51d0c-121">Wenn kein Kulturwert vorhanden ist, verwenden Sie `Culture=neutral`.</span><span class="sxs-lookup"><span data-stu-id="51d0c-121">If there is no culture value, use `Culture=neutral`.</span></span>  

<span data-ttu-id="51d0c-122">Im folgenden Codebeispiel wird gezeigt, wie Sie diese Informationen mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="51d0c-122">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  

```cpp
Assembly^ myDll =
    Assembly::Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```csharp
Assembly myDll =
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1");
```

```vb
Dim myDll As Assembly = _
    Assembly.Load("myDll, Version=1.0.0.1, Culture=neutral, PublicKeyToken=9b35aa32c18d4fb1")
```

<span data-ttu-id="51d0c-123">Sie können das Hexadezimalformat des öffentlichen Schlüssels und des öffentlichen Schlüsseltokens für eine bestimmte Assembly mithilfe des folgenden Befehls [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) ausgeben:</span><span class="sxs-lookup"><span data-stu-id="51d0c-123">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  

<span data-ttu-id="51d0c-124">**sn -Tp \<** *Assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="51d0c-124">**sn -Tp \<** *assembly* **>**</span></span>  

<span data-ttu-id="51d0c-125">Wenn Sie eine öffentliche Schlüsseldatei haben, können Sie stattdessen den folgenden Befehl verwenden. Beachten Sie aber den Unterschied bei der Groß- und Kleinschreibung bei der Befehlszeilenoption:</span><span class="sxs-lookup"><span data-stu-id="51d0c-125">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  

<span data-ttu-id="51d0c-126">**sn -tp \<** *öffentliche Schlüsseldatei* **>**</span><span class="sxs-lookup"><span data-stu-id="51d0c-126">**sn -tp \<** *public key file* **>**</span></span>  

## <a name="see-also"></a><span data-ttu-id="51d0c-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51d0c-127">See also</span></span>

- [<span data-ttu-id="51d0c-128">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="51d0c-128">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
