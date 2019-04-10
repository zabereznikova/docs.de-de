---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: b7bfcb0f2034145822922126fe61efea8d8ef269
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59344207"
---
# <a name="-libpath"></a>-libpath
Gibt den Speicherort der Assemblys verwiesen wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`dirList`|Erforderlich. Durch Semikolons getrennte Liste von Verzeichnissen, die der Compiler sucht, wenn eine referenzierte Assembly wurde nicht gefunden in entweder das aktuelle Arbeitsverzeichnis (das Verzeichnis, von dem Sie den Compiler aufrufen) oder die common Language Runtime-Systemverzeichnis. Wenn der Name des Verzeichnisses ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").|  
  
## <a name="remarks"></a>Hinweise  
 Die `-libpath` Option gibt an, den Speicherort der Assemblys, die auf die verwiesen wird durch die [-Verweis](../../../visual-basic/reference/command-line-compiler/reference.md) Option.  
  
 Der Compiler sucht in folgender Reihenfolge nach Assemblyverweisen, die nicht voll qualifiziert sind:  
  
1. Aktuelles Arbeitsverzeichnis Dies ist das Arbeitsverzeichnis, aus dem der Compiler abgerufen wird.  
  
2. Das Verzeichnis des CLR-Systems (Common Language Runtime)  
  
3. Durch angegebenen Verzeichnisse `/libpath`.  
  
4. Von den LIB-Umgebungsvariablen angegebene Verzeichnisse  
  
 Die `-libpath` -Option ist additiv; Geben sie mehr als einmal an jeden vorherigen Wert angehängt.  
  
 Verwendung `-reference` um einen Assemblyverweis anzugeben.  
  
|Zum Festlegen von/LIBPATH in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Verweise**.<br />3.  Klicken Sie auf die **Verweispfade...**  Schaltfläche.<br />4.  In der **Verweispfade** Dialogfeld Geben Sie den Namen des Verzeichnisses, in der **Ordner:** Feld.<br />5.  Klicken Sie auf **Ordner hinzufügen**.|  
  
## <a name="example"></a>Beispiel  
 Der folgende code kompiliert `T2.vb` eine .exe-Datei zu erstellen. Der Compiler sucht im Arbeitsverzeichnis, in das Stammverzeichnis von Laufwerk C: und im Verzeichnis von Laufwerk C: neuen Assemblys nach Assemblyverweisen.  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
