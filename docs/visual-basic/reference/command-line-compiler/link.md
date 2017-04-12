---
title: / Link (Visual Basic) | Microsoft-Dokumentation
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
- l compiler option [Visual Basic]
- EmbedInteropTypes
- embed interop types [COM Interop]
- -link compiler option [Visual Basic]
- /link compiler option [Visual Basic]
- link compiler option [Visual Basic]
- -l compiler option [Visual Basic]
- /l compiler option [Visual Basic]
ms.assetid: 1885f24a-86f5-486c-a064-9fb7e455ccec
caps.latest.revision: 27
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
ms.openlocfilehash: e98c855f0a0185e9d1b6682df9fc734e9f1f07bc
ms.lasthandoff: 03/13/2017

---
# <a name="link-visual-basic"></a>/link (Visual Basic)
Veranlasst den Compiler, COM-Typinformationen in den angegebenen Assemblys für das Projekt verfügbar, die Sie gerade kompilieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
/link:fileList  
' -or-  
/l:fileList  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`fileList`|Erforderlich. Durch Trennzeichen getrennte Liste von Assemblydateinamen. Wenn der Dateiname ein Leerzeichen enthält, müssen Sie den Namen in Anführungszeichen einschließen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `/link` Option ermöglicht es Ihnen, eine Anwendung bereitzustellen, die eingebetteten Typinformationen. Die Anwendung kann dann Typen in einer Assembly der Common Language Runtime verwenden, die die eingebetteten Typinformationen implementieren, ohne einen Verweis auf die Common Language Runtime-Assembly. Wenn verschiedene Versionen der Laufzeitassembly veröffentlicht werden, kann die Anwendung, die die eingebetteten Typinformationen mit verschiedenen Versionen arbeiten, ohne neu kompiliert werden. Ein Beispiel finden Sie unter [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).  
  
 Mithilfe der `/link` Option ist besonders nützlich, wenn Sie COM-Interop verwenden. Sie können COM-Typen einbetten, sodass Ihre Anwendung eine primäre Interopassembly (PIA) auf dem Zielcomputer nicht mehr erforderlich ist. Die `/link` Option weist den Compiler an, die COM-Typinformationen aus der referenzierten Interop-Assembly in den resultierenden kompilierten Code einzubetten. Der COM-Typ wird durch den Wert für die CLSID (GUID) identifiziert. Daher können Ihre Anwendung auf einem Zielcomputer ausführen, die die gleichen COM-Typen mit denselben CLSID-Werten installiert hat. Clientanwendungen, die Microsoft Office automatisieren sind ein gutes Beispiel. Da Clientanwendungen wie Office in der Regel den gleichen CLSID-Wert in den verschiedenen Versionen halten, kann die Anwendung verwiesen wird COM-Typen verwenden, wie .NET Framework 4 oder höher auf dem Zielcomputer installiert ist und die Anwendung verwendet die Methoden, Eigenschaften oder Ereignisse, die in den referenzierten COM-Typen enthalten sind.  
  
 Die `/link` -Option bettet nur Schnittstellen, Strukturen und Delegaten. Einbetten von COM-Klassen wird nicht unterstützt.  
  
> [!NOTE]
>  Wenn Sie eine Instanz eines eingebetteten COM-Typs in Ihrem Code erstellen, müssen Sie die Instanz mithilfe der entsprechenden Schnittstelle erstellen. Versuch, eine Instanz eines eingebetteten COM-Typs zu erstellen, mit CoClass verursacht einen Fehler.  
  
 Festlegen der `/link` option [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]einen Assemblyverweis hinzu, und legen die `Embed Interop Types` -Eigenschaft **true**. Die Standardeinstellung für die `Embed Interop Types` Eigenschaft **false**.  
  
 Wenn Sie eine COM-Assembly (Assembly A) verknüpfen, verweist auf eine andere COM-Assembly (Assembly B), müssen Sie auch mit der Assembly B zu verknüpfen, wenn eine der folgenden Aussagen zutrifft:  
  
-   Ein Typ von Assembly A erbt von einem Typ oder implementiert eine Schnittstelle aus Assembly B.  
  
-   Ein Feld, Eigenschaft, Ereignis oder -Methode, die einen Rückgabetyp für oder Parametertyp aus Assembly B wird aufgerufen.  
  
 Verwendung [/LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md) an das Verzeichnis, in dem eine oder mehrere der Assemblyverweise befindet.  
  
 Wie die [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) -Compileroption, die `/link` -Compileroption verwendet der Vbc.rsp-Antwortdatei, die häufig Verweise verwendet [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys. Verwenden Sie die [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) (Compileroption), wenn Sie nicht, dass den Compiler die Datei Vbc.rsp verwendet möchten.  
  
 Die Kurzform der `/link` ist `/l`.  
  
## <a name="generics-and-embedded-types"></a>Generika und eingebettete Typen  
 In den folgenden Abschnitten werden die Einschränkungen beschrieben, über die Verwendung von generischer Typen in Clientanwendungen, die Interop-Typen einbetten.  
  
### <a name="generic-interfaces"></a>Generische Schnittstellen  
 Generische Schnittstellen, die von einer Interop-Assembly eingebettet sind, können nicht verwendet werden. Dies wird im folgenden Beispiel gezeigt.  
  
 [!code-vb[VbLinkCompiler&#1;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_1.vb)]  
  
### <a name="types-that-have-generic-parameters"></a>Typen, die generische Parameter aufweisen  
 Typen, die einen generischen Parameter verfügen, deren Typ aus einer Interop-Assembly eingebettet ist, nicht wenn vorgesehen, die aus einer externen Assembly ist. Diese Einschränkung gilt nicht für Schnittstellen. Betrachten Sie z. B. die <xref:Microsoft.Office.Interop.Excel.Range>-Schnittstelle, die in definiert ist die <xref:Microsoft.Office.Interop.Excel>Assembly.</xref:Microsoft.Office.Interop.Excel> </xref:Microsoft.Office.Interop.Excel.Range> Wenn eine Bibliothek Interop-Typen aus bettet die <xref:Microsoft.Office.Interop.Excel>Assembly und stellt eine Methode, die einem generischen Typ, der einen Parameter, dessen Typ zurückgegeben wird die <xref:Microsoft.Office.Interop.Excel.Range>Schnittstelle, muss diese Methode eine generische Schnittstelle zurückgeben, wie im folgenden Codebeispiel gezeigt.</xref:Microsoft.Office.Interop.Excel.Range> </xref:Microsoft.Office.Interop.Excel>  
  
 [!code-vb[VbLinkCompiler&#2;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_2.vb)]  
[!code-vb[VbLinkCompiler&3;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_3.vb)]  
[!code-vb[VbLinkCompiler&4;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_4.vb)]  
  
 Im folgenden Beispiel Clientcode die Methode, die zurückgibt Aufrufen der <xref:System.Collections.IList>generische Schnittstelle ohne Fehler.</xref:System.Collections.IList>  
  
 [!code-vb[VbLinkCompiler&5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/link_5.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird die Quelldatei `OfficeApp.vb` und verweisen auf Assemblys aus `COMData1.dll` und `COMData2.dll` zu `OfficeApp.exe`.  
  
```vb  
vbc /link:COMData1.dll,COMData2.dll /out:OfficeApp.exe OfficeApp.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](http://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)   
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [/ LIBPATH](../../../visual-basic/reference/command-line-compiler/libpath.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Einführung in COM-Interop](../../../visual-basic/programming-guide/com-interop/introduction-to-com-interop.md)
