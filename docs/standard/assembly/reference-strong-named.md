---
title: 'Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen'
description: Dieser Artikel beschreibt, wie in einer .NET-Assembly mit starkem Namen zur Kompilierzeit oder Runtime auf Typen oder Ressourcen verwiesen wird.
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
ms.openlocfilehash: e42c1b461da16d7000605b9b9321138bbfebd307
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379877"
---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="2aa21-103">Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="2aa21-103">How to: Reference a strong-named assembly</span></span>
<span data-ttu-id="2aa21-104">Beim Verweisen auf Typen oder Ressourcen in einer Assembly mit starkem Namen handelt es sich in der Regel um einen transparenten Prozess.</span><span class="sxs-lookup"><span data-stu-id="2aa21-104">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="2aa21-105">Sie können den Verweis zur Kompilierzeit (frühes Binden) oder zur Runtime vornehmen.</span><span class="sxs-lookup"><span data-stu-id="2aa21-105">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
<span data-ttu-id="2aa21-106">Ein Verweis zur Kompilierzeit tritt auf, wenn Sie den Compiler darauf hinweisen, dass die Assembly, die kompiliert werden soll, explizit auf eine andere Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="2aa21-106">A compile-time reference occurs when you indicate to the compiler that the assembly to be compiled explicitly references another assembly.</span></span> <span data-ttu-id="2aa21-107">Beim Verweisen zur Kompilierzeit ruft der Compiler automatisch den öffentlichen Schlüssel der Zielassembly mit starkem Namen ab und platziert ihn in der Assemblyreferenz der Assembly, die aktuell kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="2aa21-107">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2aa21-108">Eine Assembly mit starkem Namen kann nur Typen aus anderen Assemblys mit starkem Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="2aa21-108">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="2aa21-109">Andernfalls ist die Sicherheit der Assembly mit starkem Namen beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="2aa21-109">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
## <a name="make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="2aa21-110">Verweisen auf eine Assembly mit starkem Namen zur Kompilierzeit</span><span class="sxs-lookup"><span data-stu-id="2aa21-110">Make a compile-time reference to a strong-named assembly</span></span>  

<span data-ttu-id="2aa21-111">Geben Sie an einer Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="2aa21-111">At a command prompt, type the following command:</span></span>  

<span data-ttu-id="2aa21-112">\<*Compilerbefehl*>  **/reference:** \<*Assemblyname*></span><span class="sxs-lookup"><span data-stu-id="2aa21-112">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  

<span data-ttu-id="2aa21-113">In diesem Befehl ist der *Compilerbefehl* der Befehl für die Sprache, die Sie verwenden, und *Assemblyname* ist der Name der Assembly mit starkem Namen, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2aa21-113">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="2aa21-114">Sie können auch andere Compileroptionen verwenden, z.B. die Option **/t:library** zum Erstellen einer Bibliothekassembly.</span><span class="sxs-lookup"><span data-stu-id="2aa21-114">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  

<span data-ttu-id="2aa21-115">Im folgenden Beispiel wird die Assembly *myAssembly.dll* erstellt, die auf die Assembly mit dem starkem Namen *myLibAssembly.dll* aus dem Codemodul *myAssembly.cs* verweist.</span><span class="sxs-lookup"><span data-stu-id="2aa21-115">The following example creates an assembly called *myAssembly.dll* that references a strong-named assembly called *myLibAssembly.dll* from a code module called *myAssembly.cs*.</span></span>  

```cmd
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  

## <a name="make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="2aa21-116">Verweisen auf eine Assembly mit starkem Namen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="2aa21-116">Make a run-time reference to a strong-named assembly</span></span>  
  
<span data-ttu-id="2aa21-117">Wenn Sie zur Laufzeit auf eine Assembly mit starkem Namen verweisen (z. B. mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>- oder <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>-Methode), müssen Sie den Anzeigenamen der Assembly mit starkem Namen verwenden, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2aa21-117">When you make a run-time reference to a strong-named assembly, for example by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> method, you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="2aa21-118">Die Syntax eines Anzeigenamens lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2aa21-118">The syntax of a display name is as follows:</span></span>  

<span data-ttu-id="2aa21-119">\<*Assemblyname*> **,** \<*Versionsnummer*> **,** \<*Kultur*> **,** \<*Token des öffentlichen Schlüssels*></span><span class="sxs-lookup"><span data-stu-id="2aa21-119">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  

<span data-ttu-id="2aa21-120">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2aa21-120">For example:</span></span>  

```console
myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33
```  

<span data-ttu-id="2aa21-121">In diesem Beispiel ist `PublicKeyToken` die hexadezimale Form des öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="2aa21-121">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="2aa21-122">Wenn kein Kulturwert vorhanden ist, verwenden Sie `Culture=neutral`.</span><span class="sxs-lookup"><span data-stu-id="2aa21-122">If there is no culture value, use `Culture=neutral`.</span></span>  

<span data-ttu-id="2aa21-123">Im folgenden Codebeispiel wird gezeigt, wie Sie diese Informationen mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="2aa21-123">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>  

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

<span data-ttu-id="2aa21-124">Sie können das Hexadezimalformat des öffentlichen Schlüssels und des öffentlichen Schlüsseltokens für eine bestimmte Assembly mithilfe des folgenden Befehls [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) ausgeben:</span><span class="sxs-lookup"><span data-stu-id="2aa21-124">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  

<span data-ttu-id="2aa21-125">**sn -Tp \<** *Assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="2aa21-125">**sn -Tp \<** *assembly* **>**</span></span>  

<span data-ttu-id="2aa21-126">Wenn Sie eine öffentliche Schlüsseldatei haben, können Sie stattdessen den folgenden Befehl verwenden. Beachten Sie aber den Unterschied bei der Groß- und Kleinschreibung bei der Befehlszeilenoption:</span><span class="sxs-lookup"><span data-stu-id="2aa21-126">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  

<span data-ttu-id="2aa21-127">**sn -tp \<** *öffentliche Schlüsseldatei* **>**</span><span class="sxs-lookup"><span data-stu-id="2aa21-127">**sn -tp \<** *public key file* **>**</span></span>  

## <a name="see-also"></a><span data-ttu-id="2aa21-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2aa21-128">See also</span></span>

- [<span data-ttu-id="2aa21-129">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="2aa21-129">Create and use strong-named assemblies</span></span>](create-use-strong-named.md)
