---
title: 'Gewusst wie: Verweisen auf eine Assembly mit starkem Namen'
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
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: aa46bfdfe42dca9509e39d4b6218473aa00a1877
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-reference-a-strong-named-assembly"></a><span data-ttu-id="4be8d-102">Gewusst wie: Verweisen auf eine Assembly mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="4be8d-102">How to: Reference a Strong-Named Assembly</span></span>
<span data-ttu-id="4be8d-103">Beim Verweisen auf Typen oder Ressourcen in einer Assembly mit starkem Namen handelt es sich in der Regel um einen transparenten Prozess.</span><span class="sxs-lookup"><span data-stu-id="4be8d-103">The process for referencing types or resources in a strong-named assembly is usually transparent.</span></span> <span data-ttu-id="4be8d-104">Sie können den Verweis zur Kompilierzeit (frühes Binden) oder zur Runtime vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4be8d-104">You can make the reference either at compile time (early binding) or at run time.</span></span>  
  
 <span data-ttu-id="4be8d-105">Ein Verweis zur Kompilierzeit tritt auf, wenn Sie den Compiler darauf hinweisen, dass Ihre Assembly explizit auf eine andere Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="4be8d-105">A compile-time reference occurs when you indicate to the compiler that your assembly explicitly references another assembly.</span></span> <span data-ttu-id="4be8d-106">Beim Verweisen zur Kompilierzeit ruft der Compiler automatisch den öffentlichen Schlüssel der Zielassembly mit starkem Namen ab und platziert ihn in der Assemblyreferenz der Assembly, die aktuell kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="4be8d-106">When you use compile-time referencing, the compiler automatically gets the public key of the targeted strong-named assembly and places it in the assembly reference of the assembly being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4be8d-107">Eine Assembly mit starkem Namen kann nur Typen aus anderen Assemblys mit starkem Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4be8d-107">A strong-named assembly can only use types from other strong-named assemblies.</span></span> <span data-ttu-id="4be8d-108">Andernfalls ist die Sicherheit der Assembly mit starkem Namen beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="4be8d-108">Otherwise, the security of the strong-named assembly would be compromised.</span></span>  
  
### <a name="to-make-a-compile-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="4be8d-109">So verweisen Sie zur Kompilierzeit auf eine Assembly mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="4be8d-109">To make a compile-time reference to a strong-named assembly</span></span>  
  
1.  <span data-ttu-id="4be8d-110">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="4be8d-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="4be8d-111">\<*Compilerbefehl*> **/reference:**\<*Assemblyname*></span><span class="sxs-lookup"><span data-stu-id="4be8d-111">\<*compiler command*> **/reference:**\<*assembly name*></span></span>  
  
     <span data-ttu-id="4be8d-112">In diesem Befehl ist der *Compilerbefehl* der Befehl für die Sprache, die Sie verwenden, und *Assemblyname* ist der Name der Assembly mit starkem Namen, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4be8d-112">In this command, *compiler command* is the compiler command for the language you are using, and *assembly name* is the name of the strong-named assembly being referenced.</span></span> <span data-ttu-id="4be8d-113">Sie können auch andere Compileroptionen verwenden, z.B. die Option **/t:library** zum Erstellen einer Bibliothekassembly.</span><span class="sxs-lookup"><span data-stu-id="4be8d-113">You can also use other compiler options, such as the **/t:library** option for creating a library assembly.</span></span>  
  
 <span data-ttu-id="4be8d-114">Im folgenden Beispiel wird eine Assembly namens `myAssembly.dll` erstellt, die auf eine Assembly mit starkem Namen namens `myLibAssembly.dll` aus einem Codemodul namens `myAssembly.cs` verweist.</span><span class="sxs-lookup"><span data-stu-id="4be8d-114">The following example creates an assembly called `myAssembly.dll` that references a strong-named assembly called `myLibAssembly.dll` from a code module called `myAssembly.cs`.</span></span>  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### <a name="to-make-a-run-time-reference-to-a-strong-named-assembly"></a><span data-ttu-id="4be8d-115">So verweisen Sie zur Runtime auf eine Assembly mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="4be8d-115">To make a run-time reference to a strong-named assembly</span></span>  
  
1.  <span data-ttu-id="4be8d-116">Wenn Sie zur Runtime auf eine Assembly mit starkem Namen verweisen (z.B. mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>- oder <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName>-Methode), müssen Sie den Anzeigenamen der referenzierten Assembly mit starkem Namen verwenden.</span><span class="sxs-lookup"><span data-stu-id="4be8d-116">When you make a run-time reference to a strong-named assembly (for example, by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> or <xref:System.Reflection.Assembly.GetType%2A?displayProperty=fullName> method), you must use the display name of the referenced strong-named assembly.</span></span> <span data-ttu-id="4be8d-117">Die Syntax eines Anzeigenamens lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="4be8d-117">The syntax of a display name is as follows:</span></span>  
  
     <span data-ttu-id="4be8d-118">\<*Assemblyname*>**,** \<*Versionsnummer*>**,** \<*Kultur*>**,** \<*öffentliches Schlüsseltoken*></span><span class="sxs-lookup"><span data-stu-id="4be8d-118">\<*assembly name*>**,** \<*version number*>**,** \<*culture*>**,** \<*public key token*></span></span>  
  
     <span data-ttu-id="4be8d-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4be8d-119">For example:</span></span>  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     <span data-ttu-id="4be8d-120">In diesem Beispiel ist `PublicKeyToken` die hexadezimale Form des öffentlichen Schlüsseltokens.</span><span class="sxs-lookup"><span data-stu-id="4be8d-120">In this example, `PublicKeyToken` is the hexadecimal form of the public key token.</span></span> <span data-ttu-id="4be8d-121">Wenn kein Kulturwert vorhanden ist, verwenden Sie `Culture=neutral`.</span><span class="sxs-lookup"><span data-stu-id="4be8d-121">If there is no culture value, use `Culture=neutral`.</span></span>  
  
 <span data-ttu-id="4be8d-122">Im folgenden Codebeispiel wird gezeigt, wie Sie diese Informationen mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="4be8d-122">The following code example shows how to use this information with the <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> method.</span></span>  
  
 <span data-ttu-id="4be8d-123">[!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)] [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)] [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="4be8d-123">[!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)] [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)] [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]</span></span>  
  
 <span data-ttu-id="4be8d-124">Sie können das Hexadezimalformat des öffentlichen Schlüssels und des öffentlichen Schlüsseltokens für eine bestimmte Assembly mithilfe des folgenden Befehls [Strong Name (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) ausgeben:</span><span class="sxs-lookup"><span data-stu-id="4be8d-124">You can print the hexadecimal format of the public key and public key token for a specific assembly by using the following [Strong Name (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) command:</span></span>  
  
 <span data-ttu-id="4be8d-125">**sn -Tp \<** *Assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="4be8d-125">**sn -Tp \<** *assembly* **>**</span></span>  
  
 <span data-ttu-id="4be8d-126">Wenn Sie eine öffentliche Schlüsseldatei haben, können Sie stattdessen den folgenden Befehl verwenden. Beachten Sie aber den Unterschied bei der Groß- und Kleinschreibung bei der Befehlszeilenoption:</span><span class="sxs-lookup"><span data-stu-id="4be8d-126">If you have a public key file, you can use the following command instead (note the difference in case on the command-line option):</span></span>  
  
 <span data-ttu-id="4be8d-127">**sn -tp \<** *Assembly* **>**</span><span class="sxs-lookup"><span data-stu-id="4be8d-127">**sn -tp \<** *assembly* **>**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4be8d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4be8d-128">See Also</span></span>  
 [<span data-ttu-id="4be8d-129">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="4be8d-129">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

