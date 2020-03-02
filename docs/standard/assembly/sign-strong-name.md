---
title: 'Vorgehensweise: Signieren einer Assembly mit einem starken Namen'
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: 9998e69e8bf1505bcfc7a9103e9d89616dad9633
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78160312"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a>Vorgehensweise: Signieren einer Assembly mit einem starken Namen

> [!NOTE]
> .NET Core unterstützt Assemblys mit starkem Namen, und alle Assemblys in der .NET Core-Bibliothek sind signiert. Für die meisten Assemblys von Drittanbietern sind jedoch keine starken Namen erforderlich. Weitere Informationen finden Sie unter [Strong Name Signing (Signieren von Assemblys mit starkem Namen)](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) auf GitHub.

Es gibt mehrere Möglichkeiten, eine Assembly mit einem starken Namen zu signieren:  
  
- Mithilfe der Registerkarte **Signierung** im Dialogfeld **Eigenschaften** eines Projekts in Visual Studio. Dies ist die einfachste und bequemste Methode, eine Assembly mit einem starken Namen zu signieren.  
  
- Mit dem [Assemblylinker-Tool (Al.exe)](../../framework/tools/al-exe-assembly-linker.md), um ein .NET Framework-Codemodul (eine *.netmodule*-Datei) mit einer Schlüsseldatei zu verknüpfen.  
  
- Mithilfe von Assemblyattributen, um die Informationen zum starken Namen in den Code einzufügen. Abhängig von dem Ort, an dem sich die zu verwendende Schlüsseldatei befindet, können Sie entweder das <xref:System.Reflection.AssemblyKeyFileAttribute> -Attribut oder das <xref:System.Reflection.AssemblyKeyNameAttribute> -Attribut verwenden.  
  
- Mithilfe von Compileroptionen.  
  
 Sie benötigen ein kryptografisches Schlüsselpaar, um eine Assembly mit einem starken Namen zu signieren. Weitere Informationen zum Erstellen eines Schlüsselpaars finden Sie unter [Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars](create-public-private-key-pair.md).  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a>Erstellen und Signieren einer Assembly mit einem starken Namen mit Visual Studio  
  
1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.  
  
2. Wählen Sie die Registerkarte **Signierung** aus.  
  
3. Wählen Sie das Feld **Assembly signieren** aus.  
  
4. Klicken Sie im Feld **Schlüsseldatei mit starkem Namen auswählen** auf **Durchsuchen**, und navigieren Sie dann zur Schlüsseldatei. Klicken Sie zum Erstellen einer neuen Schlüsseldatei auf **Neu**, und geben Sie ihren Namen in das Dialogfeld **Schlüssel für einen starken Namen erstellen** ein.  
  
> [!NOTE]
> Wählen Sie eine Datei mit öffentlichem Schlüssel aus, um [die Signierung einer Assembly zu verzögern](delay-sign.md).  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a>Erstellen und Signieren einer Assembly mit einem starken Name mithilfe des Assemblylinkers  
  
Geben Sie in der [Developer-Eingabeaufforderung für Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md) den folgenden Befehl ein:  

**al** **/out:** \<*assemblyName*>  *\<moduleName>* **/keyfile:** \<*keyfileName*>  

Ort:  

- *assemblyName* ist der Name der stark signierten Assembly (eine *DLL*- oder *EXE*-Datei), die der Assemblylinker ausgibt.  
  
- *moduleName* ist der Name eines .NET Framework-Codemoduls (eine *NETMODULE*-Datei), das mindestens einen Typ enthält. Sie können eine *NETMODULE*-Datei erstellen, indem Sie Ihren Code mit der `/target:module`-Option in C# oder Visual Basic kompilieren.
  
- *keyfileName* ist der Name des Containers oder der Datei, der bzw. die das Schlüsselpaar enthält. Der Assemblylinker interpretiert einen relativen Pfad im Zusammenhang mit dem aktuellen Verzeichnis.  

Im folgenden Beispiel wird die Assembly *MyAssembly.dll* unter Verwendung der Schlüsseldatei *sgKey.snk* mit einem starken Namen signiert.  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
Weitere Informationen über die Verwendung dieses Tools finden Sie unter [Assemblylinker](../../framework/tools/al-exe-assembly-linker.md).  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a>Signieren einer Assembly mit einem starken Namen mithilfe von Attributen  
  
1. Fügen Sie in Ihrer Codemoduldatei das <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> -Attribut oder das <xref:System.Reflection.AssemblyKeyNameAttribute> -Attribut hinzu, und geben Sie den Namen der Datei oder des Containers an, die bzw. der das zum Signieren der Assembly mit einem starken Namen zu verwendende Schlüsselpaar enthält.  

2. Kompilieren Sie die Quellcodedatei normal.  

   > [!NOTE]
   > Die C#- und Visual Basic-Compiler geben Compilerwarnungen aus (CS1699 bzw. BC41008), wenn das <xref:System.Reflection.AssemblyKeyFileAttribute> -Attribut oder das <xref:System.Reflection.AssemblyKeyNameAttribute> -Attribut im Quellcode auftreten. Sie können die Warnungen ignorieren.  

Im folgenden Beispiel wird das <xref:System.Reflection.AssemblyKeyFileAttribute>-Attribut mit der Schlüsseldatei *keyfile.snk* verwendet, die sich in dem Verzeichnis befindet, in dem die Assembly kompiliert wird.  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

Sie können auch während des Kompiliervorgangs der Quelldatei eine Assembly verzögert signieren. Weitere Informationen finden Sie unter [Verzögertes Signieren einer Assembly](delay-sign.md).  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a>Signieren einer Assembly mit einem starken Namen mithilfe des Compilers  

Kompilieren Sie Ihre Quellcodedateien mit der Compileroption `/keyfile` oder `/delaysign` in C# und Visual Basic bzw. mit der Linkeroption `/KEYFILE` oder `/DELAYSIGN` in C++. Fügen Sie nach dem Optionsnamen einen Doppelpunkt und den Namen der Schlüsseldatei hinzu. Wenn Sie einen Befehlszeilencompiler verwenden, können Sie die Schlüsseldatei in das Verzeichnis kopieren, das die Quellcodedateien enthält.  

Weitere Informationen zum verzögerten Signieren finden Sie unter [Verzögertes Signieren einer Assembly](delay-sign.md).  

Im folgenden Beispiel wird der C#-Compiler verwendet und die Assembly *UtilityLibrary.dll* mithilfe der Schlüsseldatei *sgKey.snk* mit einem starken Namen signiert.  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a>Siehe auch

- [Erstellen und Verwenden von Assemblys mit starkem Namen](create-use-strong-named.md)
- [How to: Erstellen eines öffentlichen/privaten Schlüsselpaars](create-public-private-key-pair.md)
- [Al.exe (Assembly Linker-Tool)](../../framework/tools/al-exe-assembly-linker.md)
- [Verzögertes Signieren einer Assembly](delay-sign.md)
- [Verwalten der Signierung von Assemblys und Manifesten](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [Seite „Signierung“, Projekt-Designer](/visualstudio/ide/reference/signing-page-project-designer)
