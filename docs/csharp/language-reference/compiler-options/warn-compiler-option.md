---
description: -warn (C#-Compileroptionen)
title: -warn (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: d59274423e6f9844d3ab22f3ac513ba1a05d7f07
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171350"
---
# <a name="-warn-c-compiler-options"></a>-warn (C#-Compileroptionen)

Die Option **-warn** gibt die vom Compiler anzuzeigende Warnstufe an.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a>Argumente  

 `option`  
 Die Warnstufe, die für die Kompilierung angezeigt werden soll: Niedrigere Zahlen zeigen nur schwerwiegendere Warnungen an, höhere Zahlen zeigen mehr Warnungen an. Der Wert muss 0 (null) oder eine positive ganze Zahl sein:

|Warnstufe|Bedeutung|
|-------------------|-------------|
|0|Deaktiviert die Ausgabe aller Warnungmeldungen|
|1|Zeigt schwerwiegende Warnmeldungen an|  
|2|Zeigt Warnungen der Stufe 1 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zum Ausblenden von Klassenmembern|  
|3|Zeigt Warnungen der Stufe 2 sowie bestimmte, weniger schwerwiegende Warnungen an, z.B. Warnungen zu Ausdrücken, immer nach `true` oder `false` ausgewertet werden|  
|4 (Standard)|Zeigt die Warnungen aller drei Stufen sowie informative Warnungen an|
|5|Hier werden Warnungen der Stufe 4 sowie [zusätzliche Warnungen](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) vom Compiler angezeigt, der in C# 9.0 enthalten ist.|
|Höher als Stufe 5|Jeder Wert über Stufe 5 wird wie bei Stufe 5 behandelt. Sie geben im Allgemeinen einen beliebig hohen Wert an (z. B. `9999`), um sicherzustellen, dass immer alle Warnungen vorhanden sind, wenn der Compiler mit neuen Warnstufen aktualisiert wird.|
  
## <a name="remarks"></a>Bemerkungen  

 Um Informationen zu einem Fehler oder einer Warnung zu erhalten, schlagen Sie den Fehlercode im Hilfeindex nach. Andere Möglichkeiten zum Abrufen von Informationen zu einem Fehler oder einer Warnung finden Sie unter [C#-Compilerfehler](../compiler-messages/index.md).  
  
 Verwenden Sie [-warnaserror](./warnaserror-compiler-option.md), um alle Warnungen als Fehler zu behandeln. Verwenden Sie [-nowarn](./nowarn-compiler-option.md), um bestimmte Warnungen zu deaktivieren.  
  
 **-w** ist die Kurzform von **-warn**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die Seite **Eigenschaften** des Projekts.  
  
2. Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3. Ändern Sie die Eigenschaft **Warnstufe**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.  
  
## <a name="example"></a>Beispiel  

 Kompilieren Sie `in.cs`, und konfigurieren Sie den Compiler so, dass nur Warnungen der Stufe 1 angezeigt werden:  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
