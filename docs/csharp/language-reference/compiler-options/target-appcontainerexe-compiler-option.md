---
title: -target:appcontainerexe (C#-Compileroptionen)
ms.date: 07/20/2015
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
ms.openlocfilehash: b8765f64aeb08d816ca17fce64c13e981d85145b
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2018
ms.locfileid: "42907656"
---
# <a name="-targetappcontainerexe-c-compiler-options"></a>-target:appcontainerexe (C#-Compileroptionen)
Wenn Sie die Compileroption **-target:appcontainerexe** verwenden, erstellt der Compiler eine ausführbare Windows-Datei (.exe), die in einem App-Container ausgeführt werden muss. Diese Option entspricht [-target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), ist jedoch für [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)]-Apps vorgesehen.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-target:appcontainerexe  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option legt ein Bit in der [portierbaren ausführbaren](https://msdn.microsoft.com/library/windows/desktop/ms680547(v=vs.85).aspx?id=19509) Datei (Portable Executable, PE) fest, damit die App in einem App-Container ausgeführt werden muss. Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die CreateProcess-Methode versucht, die ausführbare Datei außerhalb eines App-Containers zu starten.  
  
 Sofern Sie nicht die Option [-out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) verwenden, erhält der Name der Ausgabedatei den Namen der Eingabedatei, die die [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode enthält.  
  
 Wenn Sie diese Option in einer Eingabeaufforderung festlegen, werden alle Dateien bis zur nächsten Option namens **-out** oder **-target** verwendet, um die ausführbare Datei zu erstellen.  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a>So legen Sie diese Compileroption in der IDE fest  
  
1.  Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.  
  
2.  Wählen Sie auf der Registerkarte **Anwendung** in der Liste **Ausgabetyp** die Option **Windows Store-App** aus.  
  
     Diese Option ist nur für [!INCLUDE[win8_appname_long](~/includes/win8-appname-long-md.md)]-App-Vorlagen verfügbar.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl kompiliert `filename.cs` in eine ausführbare Windows-Datei, die nur in einem App-Container ausgeführt werden kann.  
  
```console  
csc -target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [-target (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [-target:winexe (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)  
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
