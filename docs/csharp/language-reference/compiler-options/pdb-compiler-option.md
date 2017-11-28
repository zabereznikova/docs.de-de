---
title: -pdb (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: "8"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 108244d7de49c2ff4df1ac7202e77958743b32df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="pdb-c-compiler-options"></a><span data-ttu-id="a69e9-102">/pdb (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a69e9-102">/pdb (C# Compiler Options)</span></span>
<span data-ttu-id="a69e9-103">Die Compileroption **/pdb** gibt den Namen und Speicherort der Debugsymboldatei an.</span><span class="sxs-lookup"><span data-stu-id="a69e9-103">The **/pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a69e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a69e9-104">Syntax</span></span>  
  
```console  
/pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="a69e9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="a69e9-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="a69e9-106">Der Name und Speicherort der Debugsymboldatei</span><span class="sxs-lookup"><span data-stu-id="a69e9-106">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a69e9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a69e9-107">Remarks</span></span>  
 <span data-ttu-id="a69e9-108">Wenn Sie [/debug (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) angeben, erstellt der Compiler eine PDB-Datei im gleichen Verzeichnis, in dem der Compiler die Ausgabedatei (.exe oder .dll) mit einem Dateinamen erstellt, der mit dem Namen der Ausgabedatei identisch ist.</span><span class="sxs-lookup"><span data-stu-id="a69e9-108">When you specify [/debug (C# Compiler Options)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="a69e9-109">Mit **/pdb** können Sie einen nicht standardmäßigen Dateinamen und -speicherort für die PDB-Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="a69e9-109">**/pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="a69e9-110">Diese Compileroption kann weder in der Visual Studio-Entwicklungsumgebung festgelegt werden, noch kann sie programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a69e9-110">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a69e9-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a69e9-111">Example</span></span>  
 <span data-ttu-id="a69e9-112">Kompilieren Sie `t.cs`, und erstellen Sie eine PDB-Datei mit dem Namen „tt.pdb“:</span><span class="sxs-lookup"><span data-stu-id="a69e9-112">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc /debug /pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="a69e9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a69e9-113">See Also</span></span>  
 [<span data-ttu-id="a69e9-114">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="a69e9-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="a69e9-115">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="a69e9-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
