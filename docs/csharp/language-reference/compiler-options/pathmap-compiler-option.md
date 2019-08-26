---
title: -pathmap (C#-Compileroptionen)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: 48e96d2ec2ccbea83d573c0eb3630b1591c407a9
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606629"
---
# <a name="-pathmap-c-compiler-options"></a><span data-ttu-id="cfe58-102">-pathmap (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="cfe58-102">-pathmap (C# Compiler Options)</span></span>

<span data-ttu-id="cfe58-103">Mit der Compileroption **-pathmap** wird angegeben, wie physische Pfade den Quellpfadnamen zugeordnet werden, die vom Compiler ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="cfe58-103">The **-pathmap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span>

## <a name="syntax"></a><span data-ttu-id="cfe58-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfe58-104">Syntax</span></span>

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a><span data-ttu-id="cfe58-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="cfe58-105">Arguments</span></span>

 <span data-ttu-id="cfe58-106">`path1` Vollständiger Pfad zu den Quelldateien in der aktuellen Umgebung.</span><span class="sxs-lookup"><span data-stu-id="cfe58-106">`path1` The full path to the source files in the current environment</span></span>

 <span data-ttu-id="cfe58-107">`sourcePath1` Quellpfad, der in allen Ausgabedateien `path1` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="cfe58-107">`sourcePath1` The source path substituted for `path1` in any output files.</span></span>

<span data-ttu-id="cfe58-108">Trennen Sie mehrere zugeordnete Quellpfade durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="cfe58-108">To specify multiple mapped source paths, separate each with a comma.</span></span>

## <a name="remarks"></a><span data-ttu-id="cfe58-109">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="cfe58-109">Remarks</span></span>

<span data-ttu-id="cfe58-110">Aus folgenden Gründen schreibt der Compiler den Quellpfad in die Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="cfe58-110">The compiler writes the source path into its output for the following reasons:</span></span>

1. <span data-ttu-id="cfe58-111">Der Quellpfad ersetzt ein Argument, wenn das <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> auf einen optionalen Parameter angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="cfe58-111">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="cfe58-112">Der Quellpfad ist in eine PDB-Datei eingebettet.</span><span class="sxs-lookup"><span data-stu-id="cfe58-112">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="cfe58-113">Der Pfad der PDB-Datei ist in einer PE-Datei (Portable Executable, portierbare ausführbare Datei) eingebettet.</span><span class="sxs-lookup"><span data-stu-id="cfe58-113">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

<span data-ttu-id="cfe58-114">Bei dieser Option wird jeder physische Pfad auf dem Computer, auf dem der Compiler ausgeführt wird, einem entsprechenden Pfad zugeordnet, der in die Ausgabedateien geschrieben werden sollte.</span><span class="sxs-lookup"><span data-stu-id="cfe58-114">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span>

## <a name="example"></a><span data-ttu-id="cfe58-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cfe58-115">Example</span></span>

<span data-ttu-id="cfe58-116">Kompilieren Sie `t.cs` im Verzeichnis **C:\\work\\tests**, und ordnen Sie dieses Verzeichnis **\publish** in der Ausgabe zu:</span><span class="sxs-lookup"><span data-stu-id="cfe58-116">Compile `t.cs` in the directory **C:\\work\\tests** and map that directory to **\publish** in the output:</span></span>

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a><span data-ttu-id="cfe58-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfe58-117">See also</span></span>

- [<span data-ttu-id="cfe58-118">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="cfe58-118">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="cfe58-119">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="cfe58-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
