---
description: -target:winmdobj (C#-Compileroptionen)
title: -target:winmdobj (C#-Compileroptionen)
ms.date: 07/20/2015
ms.assetid: 1819a045-659d-498a-9457-c466e902986f
ms.openlocfilehash: 66a4bddb34832705ad4779829e561afd9442be8f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139085"
---
# <a name="-targetwinmdobj-c-compiler-options"></a>-target:winmdobj (C#-Compileroptionen)
Wenn Sie die Compileroption **-target:winmdobj** verwenden, erstellt der Compiler eine WINMDOBJ-Zwischendatei, die Sie in eine binäre Windows Runtime-Datei (.winmd) konvertieren können. Die WINMD-Datei kann dann von verwalteten Sprachprogrammen und auch von JavaScript- und C++-Programmen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-target:winmdobj  
```  
  
## <a name="remarks"></a>Bemerkungen  
 Die Einstellung **winmdobj** signalisiert dem Compiler, dass ein Zwischenmodul erforderlich ist. Als Antwort darauf kompiliert Visual Studio die C#-Klassenbibliothek als WINMDOBJ-Datei. Die WINMDOBJ-Datei kann dann durch das <xref:Microsoft.Build.Tasks.WinMDExp>-Exporttool eingegeben werden, um eine Windows-Metadatendatei (.winmd) zu erzeugen. Die WINMD-Datei enthält sowohl den Code von der ursprünglichen Bibliothek als auch die WinMD-Metadaten, die von JavaScript oder C++ und von der Windows-Runtime verwendet werden.  
  
 Die Ausgabe einer Datei, die mithilfe der Compileroption **-target:winmdobj** kompiliert wird, ist für die reine Verwendung als Eingabe für das WimMDExp-Exporttool vorgesehen. Auf die WINMDOBJ-Datei selbst wird nicht direkt verwiesen.  
  
 Sofern Sie nicht die Option [-out](./out-compiler-option.md) verwenden, erhält die Ausgabedatei den Namen der ersten Eingabedatei. Eine [Main](../../programming-guide/main-and-command-args/index.md)-Methode ist nicht erforderlich.  
  
 Wenn Sie die Option -target:winmdobj an einer Eingabeaufforderung festlegen, werden alle Dateien bis zur nächsten Option **-out** oder [-target:module](./target-module-compiler-option.md) verwendet, um das Windows-Programm zu erstellen.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-ide-for-a-windows-store-app"></a>So legen Sie diese Compileroption in der Visual Studio-IDE für eine Windows Store-App fest  
  
1. Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.  
  
2. Wählen Sie die Registerkarte **Anwendung** aus.  
  
3. Wählen Sie in der Liste **Ausgabetyp** die Option **WinMD-Datei** aus.  
  
     Die Option **WinMD File** ist nur für Windows 8.x Store-App-Vorlagen verfügbar.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl kompiliert `filename.cs` in eine WINMDOBJ-Zwischendatei.  
  
```console  
csc -target:winmdobj filename.cs  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [-target (C#-Compileroptionen)](./target-compiler-option.md)
- [C#-Compileroptionen](./index.md)
