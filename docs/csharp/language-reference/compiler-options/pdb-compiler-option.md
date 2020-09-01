---
description: -pdb (C#-Compileroptionen)
title: -pdb (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: 0dcafd0fd260488922c74a2330b312e80467e779
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124915"
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="97a97-103">-pdb (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="97a97-103">-pdb (C# Compiler Options)</span></span>
<span data-ttu-id="97a97-104">Die Compileroption **-pdb** gibt den Namen und Speicherort der Debugsymboldatei an.</span><span class="sxs-lookup"><span data-stu-id="97a97-104">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97a97-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="97a97-105">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="97a97-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="97a97-106">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="97a97-107">Der Name und Speicherort der Debugsymboldatei</span><span class="sxs-lookup"><span data-stu-id="97a97-107">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97a97-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="97a97-108">Remarks</span></span>  
 <span data-ttu-id="97a97-109">Wenn Sie [-debug (C#-Compileroptionen)](./debug-compiler-option.md) angeben, erstellt der Compiler eine PDB-Datei im gleichen Verzeichnis, in dem der Compiler die Ausgabedatei (.exe oder .dll) mit einem Dateinamen erstellt, der mit dem Namen der Ausgabedatei identisch ist.</span><span class="sxs-lookup"><span data-stu-id="97a97-109">When you specify [-debug (C# Compiler Options)](./debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="97a97-110">Mit **-pdb** können Sie einen Dateinamen und -speicherort für die PDB-Datei angeben, die nicht dem Standard entsprechen.</span><span class="sxs-lookup"><span data-stu-id="97a97-110">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="97a97-111">Diese Compileroption kann weder in der Visual Studio-Entwicklungsumgebung festgelegt werden, noch kann sie programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="97a97-111">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97a97-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97a97-112">Example</span></span>  
 <span data-ttu-id="97a97-113">Kompilieren Sie `t.cs`, und erstellen Sie eine PDB-Datei mit dem Namen „tt.pdb“:</span><span class="sxs-lookup"><span data-stu-id="97a97-113">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="97a97-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97a97-114">See also</span></span>

- [<span data-ttu-id="97a97-115">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="97a97-115">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="97a97-116">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="97a97-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
