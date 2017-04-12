---
title: / doc | Microsoft-Dokumentation
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
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: 18
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
ms.openlocfilehash: 1054eb256eb7670ee0454b02fc094e0306c1218d
ms.lasthandoff: 03/13/2017

---
# <a name="doc"></a>/doc
Verarbeitet Dokumentationskommentare zu einer XML-Datei.  
  
## <a name="syntax"></a>Syntax  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Optional. Angeben von +, oder nur `/doc`, generiert der Compiler Dokumentationsinformationen und platziert diese in einer XML-Datei. Angeben von `-` entspricht dem Angeben von nicht `/doc`, verursacht keine Dokumentationsinformationen erstellt werden.|  
|`file`|Erforderlich, wenn `/doc:` verwendet wird. Gibt die XML-Ausgabedatei, die mit den Kommentaren in den Quellcodedateien der Kompilierung aufgefüllt wird. Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").|  
  
## <a name="remarks"></a>Hinweise  
 Die `/doc` option steuert, ob der Compiler eine XML-Datei generiert, die die Dokumentationskommentare enthält. Bei Verwendung der `/doc:``file` Syntax der `file` Parameter gibt den Namen der XML-Datei. Bei Verwendung von `/doc` oder `/doc+`, entnimmt der Compiler den Namen der XML-Datei der ausführbaren Datei oder Bibliothek, die die vom Compiler erstellt wird. Bei Verwendung von `/doc-` , oder geben Sie die `/doc` auswählen, erstellt der Compiler keine XML-Datei.  
  
 In Quellcodedateien können Dokumentationskommentare den folgenden Definitionen vorausgehen:  
  
-   Benutzerdefinierte Typen, z. B. ein [Klasse](../../../visual-basic/language-reference/statements/class-statement.md) oder [Schnittstelle](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Member, z. B. ein Feld [Ereignis](../../../visual-basic/language-reference/statements/event-statement.md), [Eigenschaft](../../../visual-basic/language-reference/statements/property-statement.md), [Funktion](../../../visual-basic/language-reference/statements/function-statement.md), oder [Unterroutine](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Verwenden Sie die generierte XML-Datei mit den [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] [IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense) verfügen, können Sie den Dateinamen der XML-Datei der Assembly identisch sein, Sie unterstützen möchten. Stellen Sie sicher, dass die XML-Datei im gleichen Verzeichnis wie die Assembly, damit bei der Assembly verwiesen wird die [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] -Projekt die XML-Datei befindet sich ebenfalls. XML-Dokumentationsdateien sind nicht erforderlich, damit IntelliSense funktioniert für Code in einem Projekt oder in Projekten, die von einem Projekt verwiesen wird.  
  
 Wenn Sie die Kompilierung mit `/target:module`, die XML-Datei enthält die Tags `<assembly></assembly>`. Diese Tags Geben Sie den Namen der Datei, die das Assemblymanifest für die Ausgabedatei der Kompilierung enthält.  
  
 Finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) für Methoden zum Generieren von Dokumentation aus Kommentaren im Code.  
  
|Zum Festlegen von/doc in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**. Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die **Kompilieren** Registerkarte.<br />3.  Legen Sie den Wert der **XML-Dokumentationsdatei generieren** Feld.|  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) ein Beispiel.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
