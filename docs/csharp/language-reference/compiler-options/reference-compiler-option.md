---
title: -reference (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /reference
helpviewer_keywords:
- /r compiler option [C#]
- reference compiler option [C#]
- r compiler option [C#]
- /reference compiler option [C#]
- -r compiler option [C#]
- metadata import [C#]
- public type information [C#]
- -reference compiler option [C#]
ms.assetid: 8d13e5b0-abf6-4c46-bf71-2daf2cd0a6c4
ms.openlocfilehash: 3e6a999d528be111ba2b92886f4e6e3ebf185d5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173665"
---
# <a name="-reference-c-compiler-options"></a>-reference (C#-Compileroptionen)
Die Option **-reference** veranlasst den Compiler dazu, [öffentliche](../keywords/public.md) Typinformationen in der angegebenen Datei in das aktuelle Projekt zu importieren, sodass die Verweismetadaten aus den angegebenen Assemblydateien aktiviert werden.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-reference:[alias=]filename  
-reference:filename  
```  
  
## <a name="arguments"></a>Argumente  
 `filename`  
 Der Name einer Datei, die ein Assemblymanifest enthält. Fügen Sie die separate Option **-reference** für jede Datei ein, um mehr als eine Datei zu importieren.  
  
 `alias`  
 Ein gültiger C#-Bezeichner, der einen Stammnamespace darstellt, der alle Namespaces in der Assembly enthält.  
  
## <a name="remarks"></a>Hinweise  
 Fügen Sie die Option **-reference** für jede Datei ein, um mehr als eine Datei zu importieren.  
  
 Die zu importierenden Dateien müssen ein Manifest enthalten. Die Ausgabedatei muss mit einer anderen [-target](./target-compiler-option.md)-Option als [-target:module](./target-module-compiler-option.md) kompiliert werden.  
  
 **-r** ist die Kurzform von **-reference**.  
  
 Verwenden Sie [-addmodule](./addmodule-compiler-option.md), um Metadaten aus einer Ausgabedatei zu importieren, die kein Assemblymanifest enthält.  
  
 Wenn Sie auf eine Assembly (Assembly A) verweisen, die auf eine andere Assembly (Assembly B) verweist, müssen Sie auf Assembly B verweisen, wenn:  
  
- Ein verwendeter Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.  
  
- Sie rufen ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode auf, das/die über einen Rückgabetyp oder Parametertyp von Assembly B verfügt.  
  
 Verwenden Sie [-lib](./lib-compiler-option.md), um das Verzeichnis anzugeben, in dem sich ein oder mehrere der Assemblyverweise befinden. Der Artikel **-lib** erläutert auch die Verzeichnisse, in denen der Compiler nach Assemblys sucht.  
  
 Damit der Compiler einen Typ in einer Assembly, und nicht in einem Modul, erkennen kann, muss die Auflösung des Typs durch die Definition einer Instanz des Typs erzwungen werden. Der Compiler verfügt über andere Möglichkeiten, Typnamen in einer Assembly aufzulösen. Beispielsweise wird beim Erben von einem Typ in einer Assembly der Typname vom Compiler erkannt werden.  
  
 Manchmal ist es erforderlich, auf zwei verschiedene Versionen derselben Komponente aus einer Assembly heraus zu verweisen. Verwenden Sie hierzu die Alias-Teiloption des Parameters **-reference** für jede Datei, um zwischen den beiden Dateien zu unterscheiden. Dieser Alias wird als Qualifizierer für den Namen der Komponente verwendet und wird für die Komponente in einer der Dateien aufgelöst.  
  
 Die csc-Antwortdatei (.rsp), welche auf häufig verwendete .NET Framework-Assemblys verweist, wird standardmäßig verwendet. Verwenden Sie [-noconfig](./noconfig-compiler-option.md), wenn der Compiler „csc.rsp“ nicht verwenden soll.  
  
> [!NOTE]
> Verwenden Sie in Visual Studio das Dialogfeld **Verweis hinzufügen**. Weitere Informationen finden Sie unter [How to: Add or Remove References By Using the Reference Manager](/visualstudio/ide/how-to-add-or-remove-references-by-using-the-reference-manager). Um ein gleichwertiges Verhalten zwischen Hinzufügen von Verweisen mit `-reference` und Hinzufügen von Verweisen mithilfe des Dialogfelds **Verweis hinzufügen** sicherzustellen, legen Sie die Eigenschaft **Einbetten von Interop-Typen** für die Assembly, die Sie hinzufügen möchten, auf **FALSE** fest. Der Standardwert für diese Eigenschaft ist **TRUE**.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt die Verwendung der Funktion [extern-Alias](../keywords/extern-alias.md).  
  
 Kompilieren Sie die Quelldatei, und importieren Sie Metadaten aus `grid.dll` und `grid20.dll`, die bereits zuvor kompiliert wurden. Die beiden DLLs enthalten separate Versionen derselben Komponente, und Sie verwenden zwei **-reference**-Parameter mit Aliasoptionen, um die Quelldatei zu kompilieren. Die Optionen sehen folgendermaßen aus:  

```console
-reference:GridV1=grid.dll -reference:GridV2=grid20.dll  
```
  
 Dadurch werden die externen Aliase `GridV1` und `GridV2` eingerichtet, die Sie in Ihrem Programm über eine `extern`-Anweisung verwenden:  
  
```csharp  
extern alias GridV1;  
extern alias GridV2;  
// Using statements go here.  
```  
  
 Sobald dies geschehen ist, können Sie auf das Grid-Steuerelement von `grid.dll` verweisen, indem Sie dem Namen des Steuerelements wie folgt `GridV1` voranstellen:  
  
```csharp  
GridV1::Grid  
```  
  
 Darüber hinaus können Sie auf das Grid-Steuerelement von `grid20.dll` verweisen, indem Sie dem Namen des Steuerelements wie folgt `GridV2` voranstellen:  
  
```csharp  
GridV2::Grid
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
