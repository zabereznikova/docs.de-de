---
description: -main (C#-Compileroptionen)
title: -main (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: 61e63de8082a335b448ffee1ae35170d3a1cf6b4
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125266"
---
# <a name="-main-c-compiler-options"></a>-main (C#-Compileroptionen)

Diese Option gibt die Klasse an, die den Einstiegspunkt des Programms enthält, wenn mehr als eine Klasse eine **Main**-Methode enthält.

## <a name="syntax"></a>Syntax

```console
-main:class
```

## <a name="arguments"></a>Argumente
 `class`  
 Der Typ, der die **Main**-Methode enthält.  
 Der angegebene Klassenname muss vollqualifiziert sein. Er muss den vollständigen Namespace mit der Klasse, gefolgt von dem Klassennamen enthalten. Wenn sich die `Main`-Methode beispielsweise in der `Program`-Klasse im Namespace `MyApplication.Core` befindet, muss die Compileroption `-main:MyApplication.Core.Program` lauten.

## <a name="remarks"></a>Hinweise

Wenn Ihre Kompilierung mehr als einen Typ mit einer [Main](../../programming-guide/main-and-command-args/index.md)-Methode enthält, können Sie angeben, welcher Typ die **Main**-Methode enthält, die Sie als Einstiegspunkt des Programms verwenden möchten.

Diese Option wird verwendet, wenn eine *EXE*-Datei kompiliert wird.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie die Seite **Eigenschaften** des Projekts.

2. Klicken Sie auf die Eigenschaftenseite **Anwendung**.

3. Ändern Sie die Eigenschaft **Startobjekt**.

    Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.

### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a>So legen Sie diese Compileroption fest, indem Sie die *CSPROJ*-Datei manuell bearbeiten

Sie können diese Option festlegen, indem Sie die CSPROJ-Datei bearbeiten und innerhalb des `PropertyGroup`-Abschnitts ein Element `StartupObject` hinzufügen. Zum Beispiel:

```xml
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a>Beispiel

Kompilieren Sie `t2.cs` und `t3.cs`, und geben Sie so an, dass die Methode **Main** in `Test2` gefunden wird:

```console
csc t2.cs t3.cs -main:Test2
```

## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
