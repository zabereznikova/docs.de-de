---
title: -moduleassemblyname (C#-Compileroption)
ms.date: 07/20/2015
f1_keywords:
- /moduleassemblyname
helpviewer_keywords:
- moduleassemblyname compiler option [C#]
- /moduleassemblyname compiler option [C#]
- .moduleassemblyname compiler option [C#]
ms.assetid: d464d9b9-f18d-423b-95e9-66c7878fd53a
ms.openlocfilehash: 1477eeb0f2e16e18cb86009739bc8e7d9dee2ac0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173717"
---
# <a name="-moduleassemblyname-c-compiler-option"></a><span data-ttu-id="55c60-102">-moduleassemblyname (C#-Compileroption)</span><span class="sxs-lookup"><span data-stu-id="55c60-102">-moduleassemblyname (C# Compiler Option)</span></span>
<span data-ttu-id="55c60-103">Gibt eine Assembly an, auf deren nicht öffentliche Typen ein .NET-Modul zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="55c60-103">Specifies an assembly whose non-public types a .netmodule can access.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55c60-104">Syntax</span></span>  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a><span data-ttu-id="55c60-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="55c60-105">Arguments</span></span>  
 `assembly_name`  
 <span data-ttu-id="55c60-106">Der Name einer Assembly, auf deren nicht öffentliche Typen die NETMODULE-Datei zugreifen kann</span><span class="sxs-lookup"><span data-stu-id="55c60-106">The name of the assembly whose non-public types the .netmodule can access.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55c60-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55c60-107">Remarks</span></span>  
 <span data-ttu-id="55c60-108">**-moduleassemblyname** sollte beim Erstellen einer NETMODULE-Datei und wenn die folgenden Bedingungen erfüllt sind verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="55c60-108">**-moduleassemblyname** should be used when building a .netmodule, and where the following conditions are true:</span></span>  
  
- <span data-ttu-id="55c60-109">Die NETMODULE-Datei benötigt Zugriff auf nicht öffentliche Typen in einer vorhandenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="55c60-109">The .netmodule needs access to non-public types in an existing assembly.</span></span>  
  
- <span data-ttu-id="55c60-110">Sie kennen den Namen der Assembly, in die die NETMODULE-Datei integriert wird.</span><span class="sxs-lookup"><span data-stu-id="55c60-110">You know the name of the assembly into which the .netmodule will be built.</span></span>  
  
- <span data-ttu-id="55c60-111">Die vorhandene Assembly hat der Assembly, in die die NETMODULE-Datei integriert wird, Friend-Assembly-Zugriff erteilt.</span><span class="sxs-lookup"><span data-stu-id="55c60-111">The existing assembly has granted friend assembly access to the assembly into which the .netmodule will be built.</span></span>  
  
 <span data-ttu-id="55c60-112">Weitere Informationen zum Erstellen einer NETMODULE-Datei finden Sie unter [-target:module (C#-Compileroptionen)](./target-module-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="55c60-112">For more information on building a .netmodule, see [-target:module (C# Compiler Options)](./target-module-compiler-option.md).</span></span>  
  
 <span data-ttu-id="55c60-113">Weitere Informationen finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="55c60-113">For more information on friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
 <span data-ttu-id="55c60-114">Diese Option steht nicht in der Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="55c60-114">This option is not available from within the development environment; it is only available when compiling from the command line.</span></span>  
  
 <span data-ttu-id="55c60-115">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="55c60-115">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55c60-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55c60-116">Example</span></span>  
 <span data-ttu-id="55c60-117">In diesem Beispiel wird eine Assembly mit einem privaten Typ erstellt, und die Friend-Assembly-erhält Zugriff auf eine Assembly namens „csman_an_assembly“.</span><span class="sxs-lookup"><span data-stu-id="55c60-117">This sample builds an assembly with a private type, and that gives friend assembly access to an assembly called csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_1.cs  
// compile with: -target:library  
using System;  
using System.Runtime.CompilerServices;  
  
[assembly:InternalsVisibleTo ("csman_an_assembly")]  
  
class An_Internal_Class
{  
    public void Test()
    {
        Console.WriteLine("An_Internal_Class.Test called");
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="55c60-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55c60-118">Example</span></span>  
 <span data-ttu-id="55c60-119">In diesem Beispiel wird eine NETMODULE-Datei erstellt, das auf einen nicht öffentlichen Typ in der Assembly „moduleassemblyname_1.dll“ zugreift.</span><span class="sxs-lookup"><span data-stu-id="55c60-119">This sample builds a .netmodule that accesses a non-public type in the assembly moduleassemblyname_1.dll.</span></span> <span data-ttu-id="55c60-120">Da bekannt ist, dass die NETMODULE-Datei in eine Assembly namens „csman_an_assembly“ integriert wird, kann **-moduleassemblyname** angegeben werden. Dadurch wird es der NETMODULE-Datei ermöglicht, auf nicht öffentliche Typen in einer Assembly zuzugreifen, die Friend-Assembly-Zugriff auf „csman_an_assembly“ zulässt.</span><span class="sxs-lookup"><span data-stu-id="55c60-120">By knowing that this .netmodule will be built into an assembly called csman_an_assembly, we can specify **-moduleassemblyname**, allowing the .netmodule to access non-public types in an assembly that has granted friend assembly access to csman_an_assembly.</span></span>  
  
```csharp  
// moduleassemblyname_2.cs  
// compile with: -moduleassemblyname:csman_an_assembly -target:module -reference:moduleassemblyname_1.dll  
class B {  
    public void Test() {  
        An_Internal_Class x = new An_Internal_Class();  
        x.Test();  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="55c60-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55c60-121">Example</span></span>  
 <span data-ttu-id="55c60-122">In diesem Codebeispiel wird die Assembly „csman_an_assembly“ erstellt, die auf die zuvor erstellte Assembly und eine NETMODULE-Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="55c60-122">This code sample builds the assembly csman_an_assembly, referencing the previously-built assembly and .netmodule.</span></span>  
  
```csharp  
// csman_an_assembly.cs  
// compile with: -addmodule:moduleassemblyname_2.netmodule -reference:moduleassemblyname_1.dll  
class A {  
    public static void Main() {  
        B bb = new B();  
        bb.Test();  
    }  
}  
```  
  
<span data-ttu-id="55c60-123">**An_Internal_Class.Test** aufgerufen</span><span class="sxs-lookup"><span data-stu-id="55c60-123">**An_Internal_Class.Test called**</span></span>

## <a name="see-also"></a><span data-ttu-id="55c60-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55c60-124">See also</span></span>

- [<span data-ttu-id="55c60-125">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="55c60-125">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="55c60-126">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="55c60-126">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
