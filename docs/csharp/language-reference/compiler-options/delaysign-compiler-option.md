---
title: -delaysign (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /delaysign
dev_langs:
- CSharp
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce4c9fbb14081764985f3b02988dff9ee272c451
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="delaysign-c-compiler-options"></a><span data-ttu-id="e8121-102">/delaysign (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="e8121-102">/delaysign (C# Compiler Options)</span></span>
<span data-ttu-id="e8121-103">Durch diese Option reserviert der Compiler Speicherplatz in der Ausgabedatei, damit digitale Signaturen später hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="e8121-103">This option causes the compiler to reserve space in the output file so that a digital signature can be added later.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8121-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8121-104">Syntax</span></span>  
  
```console  
/delaysign[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e8121-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e8121-105">Arguments</span></span>  
 <span data-ttu-id="e8121-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e8121-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="e8121-107">Verwenden Sie **/delaysign-**, wenn die Assembly vollständig signiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8121-107">Use **/delaysign-** if you want a fully signed assembly.</span></span> <span data-ttu-id="e8121-108">Verwenden Sie **/delaysign+**, wenn Sie nur den öffentlichen Schlüssel in der Assembly platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e8121-108">Use **/delaysign+** if you only want to place the public key in the assembly.</span></span> <span data-ttu-id="e8121-109">Der Standardwert ist **/delaysign-**.</span><span class="sxs-lookup"><span data-stu-id="e8121-109">The default is **/delaysign-**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8121-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8121-110">Remarks</span></span>  
 <span data-ttu-id="e8121-111">Die Option **/delaysign** hat keine Auswirkung, wenn Sie nicht mit [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) oder [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e8121-111">The **/delaysign** option has no effect unless used with [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) or [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span>  
  
 <span data-ttu-id="e8121-112">Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert.</span><span class="sxs-lookup"><span data-stu-id="e8121-112">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="e8121-113">Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e8121-113">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="e8121-114">Wenn eine Assembly mit Verzögerung signiert wird, wird die Signatur vom Compiler nicht berechnet und gespeichert, sondern lediglich ein Bereich in der Datei reserviert, damit die Signatur zu einem späteren Zeitpunkt hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e8121-114">When an assembly is delay signed, the compiler does not compute and store the signature, but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="e8121-115">Mit **/delaysign+** können Tester die Assembly beispielsweise im globalen Cache ablegen.</span><span class="sxs-lookup"><span data-stu-id="e8121-115">For example, using **/delaysign+** allows a tester to put the assembly in the global cache.</span></span> <span data-ttu-id="e8121-116">Nach dem Testen können Sie die Assembly vollständig signieren, indem Sie den privaten Schlüssel der Assembly mithilfe des Hilfsprogramms [Assembly Linker](https://msdn.microsoft.com/library/c405shex) platzieren.</span><span class="sxs-lookup"><span data-stu-id="e8121-116">After testing, you can fully sign the assembly by placing the private key in the assembly using the [Assembly Linker](https://msdn.microsoft.com/library/c405shex) utility.</span></span>  
  
 <span data-ttu-id="e8121-117">Weitere Informationen finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](https://msdn.microsoft.com/library/xwb8f617) und [Verzögertes Signieren einer Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span><span class="sxs-lookup"><span data-stu-id="e8121-117">For more information, see [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e8121-118">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="e8121-118">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="e8121-119">Öffnen Sie die Seite **Eigenschaften** für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="e8121-119">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="e8121-120">Bearbeiten Sie die Eigenschaft **Nur verzögerte Signierung**.</span><span class="sxs-lookup"><span data-stu-id="e8121-120">Modify the **Delay sign only** property.</span></span>  
  
 <span data-ttu-id="e8121-121">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8121-121">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8121-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8121-122">See Also</span></span>  
 <span data-ttu-id="e8121-123">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8121-123">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="e8121-124">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="e8121-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

