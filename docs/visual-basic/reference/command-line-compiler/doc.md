---
title: /doc
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1f9d4f584f217e6996a499614b97f184b28664f8
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|`+` &#124; `-`|Dies ist optional. Angeben von +, oder nur `/doc`, bewirkt, dass der Compiler Dokumentationsinformationen generieren und in eine XML-Datei zu speichern. Angeben von `-` entspricht der Angabe von nicht `/doc`, verursachen keine Dokumentationsinformationen erstellt werden.|  
|`file`|Erforderlich, wenn `/doc:` verwendet wird. Gibt die XML-Ausgabedatei, die mit den Kommentaren in den Quellcodedateien der Kompilierung aufgefüllt wird. Wenn der Dateiname ein Leerzeichen enthält, setzen Sie den Namen in Anführungszeichen ("").|  
  
## <a name="remarks"></a>Hinweise  
 Die `/doc` option steuert, ob der Compiler eine XML-Datei generiert, die die Dokumentationskommentare enthält. Bei Verwendung der `/doc:``file` Syntax, die `file` Parameter gibt den Namen der XML-Datei. Bei Verwendung von `/doc` oder `/doc+`, nimmt der Compiler den Namen der XML-Datei aus der ausführbaren Datei oder Bibliothek, die der Compiler erstellt wird. Bei Verwendung von `/doc-` , oder geben Sie die `/doc` -Option der Compiler erstellt keine XML-Datei.  
  
 In den Quellcodedateien können die folgenden Definitionen von Dokumentationskommentare vorangestellt sein:  
  
-   Benutzerdefinierte Typen, z. B. eine [Klasse](../../../visual-basic/language-reference/statements/class-statement.md) oder [Schnittstelle](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
-   Elemente, z. B. ein Feld [Ereignis](../../../visual-basic/language-reference/statements/event-statement.md), [Eigenschaft](../../../visual-basic/language-reference/statements/property-statement.md), [Funktion](../../../visual-basic/language-reference/statements/function-statement.md), oder [Unterroutine](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
 Verwenden Sie die generierte XML-Datei mit den [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) feature, lassen Sie den Dateinamen der XML-Datei der Assembly identisch sein, Sie unterstützen möchten. Stellen Sie sicher, dass die XML-Datei im gleichen Verzeichnis wie die Assembly, damit bei der Assembly verwiesen wird die [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] -Projekt die XML-Datei befindet sich ebenfalls. XML-Dokumentationsdateien sind nicht erforderlich, damit IntelliSense funktioniert für Code in einem Projekt oder in Projekten, die von einem Projekt verwiesen wird.  
  
 Wenn beim Kompilieren mit `/target:module`, die XML-Datei enthält die Tags `<assembly></assembly>`. Diese Tags Geben Sie den Namen der Datei, die das Assemblymanifest für die Ausgabedatei der Kompilierung enthält.  
  
 Finden Sie unter [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) für Methoden zum Generieren von Dokumentation von den Kommentaren im Code.  
  
|Zum Festlegen von/doc in Visual Studio integrierte Entwicklungsumgebung|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Legen Sie den Wert der **generieren XML-Dokumentationsdatei** Feld.|  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) ein Beispiel.  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
