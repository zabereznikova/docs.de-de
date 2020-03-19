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
ms.openlocfilehash: cb4dbadfa4efd0750ffd3dea88a3f661e2f85a8e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173769"
---
# <a name="-checked-c-compiler-options"></a>-checked (C#-Compileroptionen)
Die Option **-checked** gibt an, ob eine Anweisung der Ganzzahlarithmetik, die einen Wert außerhalb des Bereichs des Datentyps nach sich zieht und sich nicht im Bereich eines [checked](../keywords/checked.md)- oder [unchecked](../keywords/unchecked.md)-Schlüsselworts befindet, eine Ausnahme verursacht.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a>Hinweise  
 Eine Anweisung der Ganzzahlarithmetik, die im Rahmen eines `checked`- oder `unchecked`-Schlüsselworts liegt, ist nicht der Auswirkung der Option **-checked** unterworfen.  
  
 Wenn eine Anweisung der Ganzzahlarithmetik, die sich nicht im Rahmen eines `checked`- oder `unchecked`-Schlüsselworts befindet, einen Wert außerhalb des Bereichs des Datentyps ergibt, und **-checked+** (oder **-checked**) in der Kompilierung verwendet wird, löst die Anweisung zur Laufzeit eine Ausnahme aus. Wenn **-checked-** in der Kompilierung verwendet wird, löst die Anweisung zur Laufzeit keine Ausnahme aus.  
  
 Der Standardwert für diese Option lautet **-checked-** ; die Überlaufüberprüfung ist deaktiviert.

 Automatisierte Tools zum Erstellen großer Anwendungen legen „-checked-“ manchmal auf „-checked+“ fest. Ein Szenario für die Verwendung von „-checked-“ ist die Überschreibung des globalen Standards des Tools durch Angabe von „-checked-“.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die **Eigenschaftenseite** des Projekts. Weitere Informationen finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2. Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3. Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4. Bearbeiten Sie die Eigenschaft **Auf arithmetischen Überlauf überprüfen**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl kompiliert `t2.cs`. Die Verwendung von `-checked` im Befehl gibt an, ob eine Anweisung der Ganzzahlarithmetik in der Datei, die einen Wert außerhalb des Bereichs des `checked`- oder `unchecked`-Schlüsselworts enthält und einen Wert außerhalb des Bereichs des Datentyps auslöst, zur Laufzeit eine Ausnahme verursacht.  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
