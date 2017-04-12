---
title: / bugreport | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9c64ec49d7e6842edbc0fed7407a34132a8f5a88
ms.lasthandoff: 03/13/2017

---
# <a name="bugreport"></a>/bugreport
Erstellt eine Datei, die Sie verwenden können, wenn Sie einen Fehlerbericht speichern.  
  
## <a name="syntax"></a>Syntax  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`file`|Erforderlich. Der Name der Datei, die den Problembericht enthalten wird. Schließen Sie den Dateinamen in Anführungszeichen (""), wenn der Name ein Leerzeichen enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Informationen hinzugefügt `file`:  
  
-   Eine Kopie der alle Quellcodedateien in der Kompilierung.  
  
-   Eine Liste der Compileroptionen in der Kompilierung verwendet werden soll.  
  
-   Versionsinformationen über den Compiler, gemeinsame Sprachlaufzeit und Betriebssystem.  
  
-   Compilerausgabe, falls vorhanden.  
  
-   Eine Beschreibung des Problems, für die Sie dazu aufgefordert werden.  
  
-   Eine Beschreibung Ihres das Problem Vorschlags sollte behoben werden, für die Sie dazu aufgefordert werden.  
  
 Da eine Kopie aller Quellcodedateien in enthaltene `file`, Sie möchten den (vermuteten) Codefehler in einem möglichst kurzen Programm zu reproduzieren.  
  
> [!IMPORTANT]
>  Die `/bugreport` -Option erstellt eine Datei, die möglicherweise vertrauliche Informationen enthält. Dies schließt die aktuelle Uhrzeit, Compilerversion [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Version, Betriebssystemversion, Benutzername, die Befehlszeilenargumente, mit denen der Compiler ausgeführt wurde, der gesamte Quellcode und die binäre Form eines referenzierten Assemblys. Diese Option kann durch Angabe von Befehlszeilenoptionen in der Datei Web.config für eine serverseitige Kompilierung zugegriffen werden eine [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] Anwendung. Um dies zu verhindern, ändern Sie die Datei Machine.config zum Verweigern von Benutzern auf dem Server zu kompilieren.  
  
 Wenn diese Option verwendet wird, mit `/errorreport:prompt`, `/errorreport:queue`, oder `/errorreport:send`, und der Anwendung auftritt, einen interner Compilerfehler, die Informationen im `file` an die Microsoft Corporation gesendet. Diese Informationen helfen Microsoft-Technikern, die Ursache des Fehlers zu identifizieren und die nächste Version von zu verbessern [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. Standardmäßig ist keine Informationen an Microsoft gesendet. Allerdings beim Kompilieren einer Anwendung mit `/errorreport:queue`, die standardmäßig aktiviert ist, sammelt die Anwendung ihre Fehlerberichte. Klicken Sie dann, wenn der Administrator des Computers anmeldet, wird Fehler reporting ein Popup-Fenster, mit der Administratoren zum Weiterleiten an Microsoft Fehler meldet, die seit der Anmeldung aufgetreten sind.  
  
> [!NOTE]
>  Die `/bugreport` Option ist nicht verfügbar in der Visual Studio Development Environment; es kann nur, wenn Sie über die Befehlszeile kompilieren.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel kompiliert `T2.vb` und alle Informationen in der Datei `Problem.txt`.  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ Debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [/ errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [TrustLevel-Element für SecurityPolicy ((ASP.NET Settings Schema)](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)
