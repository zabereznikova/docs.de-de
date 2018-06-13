---
title: -checked (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: 4ed8467b0e1923aedf38edfd4a25414cbcb88b7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218311"
---
# <a name="-checked-c-compiler-options"></a>-checked (C#-Compileroptionen)
Die Option **-checked** gibt an, ob eine Anweisung der Ganzzahlarithmetik, die einen Wert außerhalb des Bereichs des Datentyps nach sich zieht und sich nicht im Bereich eines [checked](../../../csharp/language-reference/keywords/checked.md)- oder [unchecked](../../../csharp/language-reference/keywords/unchecked.md)-Schlüsselworts befindet, eine Ausnahme verursacht.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine Anweisung der Ganzzahlarithmetik, die im Rahmen eines `checked`- oder `unchecked`-Schlüsselworts liegt, ist nicht der Auswirkung der Option **-checked** unterworfen.  
  
 Wenn eine Anweisung der Ganzzahlarithmetik, die sich nicht im Rahmen eines `checked`- oder `unchecked`-Schlüsselworts befindet, einen Wert außerhalb des Bereichs des Datentyps ergibt, und **-checked+** (**-checked**) in der Kompilierung verwendet wird, löst die Anweisung zur Laufzeit eine Ausnahme aus. Wenn **-checked-** in der Kompilierung verwendet wird, löst die Anweisung zur Laufzeit keine Ausnahme aus.  
  
 Der Standardwert für diese Option ist **-checked-**. Ein Szenario für die Verwendung von **-checked-** liegt in der Erstellung großer Anwendungen. Manchmal werden automatisierte Tools zum Erstellen solcher Anwendungen verwendet. Ein solches Tool könnte **-checked** automatisch auf + festlegen. Sie können die allgemeine Standardeinstellung des Tools überschreiben, indem Sie **-checked-** angeben.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaftenseite** des Projekts. Weitere Informationen finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4.  Bearbeiten Sie die Eigenschaft **Auf arithmetischen Über-/Unterlauf überprüfen**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl kompiliert `t2.cs`. Die Verwendung von `-checked` im Befehl gibt an, ob eine Anweisung der Ganzzahlarithmetik in der Datei, die einen Wert außerhalb des Bereichs des `checked`- oder `unchecked`-Schlüsselworts enthält und einen Wert außerhalb des Bereichs des Datentyps auslöst, zur Laufzeit eine Ausnahme verursacht.  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)  
 [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)  
