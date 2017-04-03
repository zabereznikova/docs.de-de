---
title: /target:appcontainerexe (C#-Compileroptionen) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e7e62229-23ea-4e53-bef5-380d951bf95f
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 168771506692308bc9b031df5c059e58e8d190b1
ms.lasthandoff: 03/13/2017

---
# <a name="targetappcontainerexe-c-compiler-options"></a>/target:appcontainerexe (C#-Compileroptionen)
Wenn Sie die Compileroption **/target:appcontainerexe** verwenden, erstellt der Compiler eine ausführbare Windows-Datei (.exe), die in einem App-Container ausgeführt werden muss. Diese Option entspricht [/target:winexe](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md), ist aber für [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)]-Apps vorgesehen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/target:appcontainerexe  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option legt ein Bit in der [portierbaren ausführbaren](http://go.microsoft.com/fwlink/p/?LinkId=236960) Datei (Portable Executable, PE) fest, damit die App in einem App-Container ausgeführt werden muss. Wenn dieses Bit festgelegt ist, tritt ein Fehler auf, wenn die CreateProcess-Methode versucht, die ausführbare Datei außerhalb eines App-Containers zu starten.  
  
 Sofern Sie nicht die Option [/out](../../../csharp/language-reference/compiler-options/out-compiler-option.md) verwenden, erhält der Name der Ausgabedatei den Namen der Eingabedatei, die die [Main](../../../csharp/programming-guide/main-and-command-args/index.md)-Methode enthält.  
  
 Wenn Sie diese Option in einer Eingabeaufforderung festlegen, werden alle Dateien bis zur nächsten Option namens **/out**- oder **/target** verwendet, um die ausführbare Datei zu erstellen.  
  
### <a name="to-set-this-compiler-option-in-the-ide"></a>So legen Sie diese Compileroption in der IDE fest  
  
1.  Öffnen Sie im **Projektmappen-Explorer** das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften** aus.  
  
2.  Wählen Sie auf der Registerkarte **Anwendung** in der Liste **Ausgabetyp** die Option **Windows Store-App** aus.  
  
     Diese Option ist nur für [!INCLUDE[win8_appname_long](../../../csharp/includes/win8_appname_long_md.md)]-App-Vorlagen verfügbar.  
  
 Informationen zum programmatischen Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl kompiliert `filename.cs` in eine ausführbare Windows-Datei, die nur in einem App-Container ausgeführt werden kann.  
  
```  
csc /target:appcontainerexe filename.cs  
```  
  
## <a name="see-also"></a>Siehe auch  
 [/target (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [/target:winexe (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/target-winexe-compiler-option.md)   
 [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
