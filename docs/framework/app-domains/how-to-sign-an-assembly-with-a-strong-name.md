---
title: 'Vorgehensweise: Signieren einer Assembly mit einem starken Namen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5580b6d8af7319397ad7eb6416941c2be0dcdb76
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303420"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a>Vorgehensweise: Signieren einer Assembly mit einem starken Namen
Es gibt mehrere Möglichkeiten, eine Assembly mit einem starken Namen zu signieren:  
  
-   Mithilfe der Registerkarte **Signierung** im Dialogfeld **Eigenschaften** eines Projekts in Visual Studio. Dies ist die einfachste und bequemste Methode, eine Assembly mit einem starken Namen zu signieren.  
  
-   Mit dem [Assemblylinker-Tool (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) , um ein .NET Framework-Codemodul (eine NETMODULE-Datei) mit einer Schlüsseldatei zu verknüpfen.  
  
-   Mithilfe von Assemblyattributen, um die Informationen zum starken Namen in den Code einzufügen. Abhängig von dem Ort, an dem sich die zu verwendende Schlüsseldatei befindet, können Sie entweder das <xref:System.Reflection.AssemblyKeyFileAttribute> -Attribut oder das <xref:System.Reflection.AssemblyKeyNameAttribute> -Attribut verwenden.  
  
-   Mithilfe von Compileroptionen.  
  
 Sie benötigen ein kryptografisches Schlüsselpaar, um eine Assembly mit einem starken Namen zu signieren. Weitere Informationen zum Erstellen eines Schlüsselpaars finden Sie unter [Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a>So erstellen und signieren Sie eine Assembly mit einem starken Namen mithilfe von Visual Studio  
  
1. Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.  
  
2. Wählen Sie die Registerkarte **Signierung** aus.  
  
3. Wählen Sie das Feld **Assembly signieren** aus.  
  
4. Wählen Sie im Feld **Schlüsseldatei mit starkem Namen auswählen** die Option **\<Durchsuchen…>** aus, und navigieren Sie dann zur Schlüsseldatei. Wählen Sie zum Erstellen einer neuen Schlüsseldatei **\<Neu…>** aus, und geben Sie ihren Namen im Dialogfeld **Schlüssel für einen starken Namen erstellen** ein.  
  
> [!NOTE]
>  Wählen Sie eine Datei mit öffentlichem Schlüssel aus, um [die Signierung einer Assembly zu verzögern](../../../docs/framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a>So erstellen und signieren Sie eine Assembly mit einem starken Namen unter Verwendung des Assemblylinkers  
  
-   Geben Sie an der [Developer-Eingabeaufforderung für Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md) den folgenden Befehl ein:  
  
     **al** **/out:**\<*Assemblyname*> *\<Modulname>* **/keyfile:**\<*Schlüsseldateiname*>  
  
     Dabei gilt:  
  
     *assemblyName*  
     Der Name der stark signierten Assembly (eine DLL- oder EXE-Datei), die der Assemblylinker ausgibt.  
  
     *moduleName*  
     Der Name eines .NET Framework-Codemoduls (eine NETMODULE-Datei), das mindestens einen Typen enthält. Sie können eine NETMODULE-Datei erstellen, indem Sie Code mit dem Schalter `/target:module` in C# oder Visual Basic kompilieren.  
  
     *keyfileName*  
     Der Name des Containers oder der Datei, der bzw. die das Schlüsselpaar enthält. Assemblylinker interpretiert einen relativen Pfad in Beziehung zum aktuellen Verzeichnis.  
  
 Im folgenden Beispiel wird die Assembly `MyAssembly.dll` unter Verwendung der Schlüsseldatei `sgKey.snk`mit einem starken Namen signiert.  
  
```  
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
 Weitere Informationen über die Verwendung dieses Tools finden Sie unter [Assemblylinker](../../../docs/framework/tools/al-exe-assembly-linker.md).  
  
#### <a name="to-sign-an-assembly-with-a-strong-name-by-using-attributes"></a>So signieren Sie eine Assembly mit einem starken Namen unter Verwendung von Attributen  
  
1. Fügen Sie in Ihrer Codemoduldatei das <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> -Attribut oder das <xref:System.Reflection.AssemblyKeyNameAttribute> -Attribut hinzu, und geben Sie den Namen der Datei oder des Containers an, die bzw. der das zum Signieren der Assembly mit einem starken Namen zu verwendende Schlüsselpaar enthält.  
  
2. Kompilieren Sie die Quellcodedatei normal.  
  
> [!NOTE]
>  Die C#- und Visual Basic-Compiler geben Compilerwarnungen aus (CS1699 bzw. BC41008), wenn das <xref:System.Reflection.AssemblyKeyFileAttribute> -Attribut oder das <xref:System.Reflection.AssemblyKeyNameAttribute> -Attribut im Quellcode auftreten. Sie können die Warnungen ignorieren.  
  
 Im folgenden Beispiel wird das <xref:System.Reflection.AssemblyKeyFileAttribute> -Attribut mit der Schlüsseldatei `keyfile.snk`verwendet, die sich in dem Verzeichnis befindet, in dem die Assembly kompiliert wird.  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
 Sie können auch während des Kompiliervorgangs der Quelldatei eine Assembly verzögert signieren. Weitere Informationen finden Sie unter [Verzögertes Signieren einer Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a>So signieren Sie eine Assembly mit einem starken Namen unter Verwendung des Compilers  
  
-   Kompilieren Sie Ihre Quellcodedateien mit der Compileroption `/keyfile` oder `/delaysign` in C# und Visual Basic bzw. mit der Linkeroption `/KEYFILE` oder `/DELAYSIGN` in C++. Fügen Sie nach dem Optionsnamen einen Doppelpunkt und den Namen der Schlüsseldatei hinzu. Wenn Sie einen Befehlszeilencompiler verwenden, können Sie die Schlüsseldatei in das Verzeichnis kopieren, das die Quellcodedateien enthält.  
  
     Informationen zum verzögerten Signieren finden Sie unter [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).  
  
     Im folgenden Beispiel wird der C#-Compiler verwendet und die Assembly `UtilityLibrary.dll` mithilfe der Schlüsseldatei `sgKey.snk` mit einem starken Namen signiert.  
  
    ```  
    csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
- [Vorgehensweise: Erstellen eines öffentlichen/privaten Schlüsselpaars](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [Al.exe (Assembly Linker-Tool)](../../../docs/framework/tools/al-exe-assembly-linker.md)
- [Verzögertes Signieren einer Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md)
- [Verwalten der Signierung von Assemblys und Manifesten](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [Seite "Signierung", Projekt-Designer](/visualstudio/ide/reference/signing-page-project-designer)
