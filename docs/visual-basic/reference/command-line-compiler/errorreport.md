---
title: / errorreport | Microsoft-Dokumentation
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
- -errorreport compiler option [Visual Basic]
- /errorreport compiler option [Visual Basic]
- errorreport compiler option [Visual Basic]
ms.assetid: a7fe83a2-a6d8-460c-8dad-79a8f433f501
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ebe5646256926f68a1a900b91c25a1768505785
ms.lasthandoff: 03/13/2017

---
# <a name="errorreport"></a>/errorreport
Gibt an, wie interne Compilerfehler vom [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Compiler gemeldet werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/errorreport:{ prompt | queue | send | none }  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Option bietet eine komfortable Möglichkeit, einen [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] interner Compilerfehler (ICE) auf dem [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Team bei Microsoft. Standardmäßig sendet der Compiler keine Informationen an Microsoft. Wenn Sie einen internen Fehler auftreten, kann jedoch diese Option auf den Fehler an Microsoft senden. Diese Informationen helfen Microsoft-Technikern, die Ursache zu identifizieren und die nächste Version von zu verbessern [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Die Fähigkeit eines Benutzers zum Senden von Berichten hängt vom Computer und den Benutzerberechtigungen ab.  
  
 Die folgende Tabelle enthält die Auswirkung der `/errorreport` Option.  
  
|Option|Verhalten|  
|---|---|  
|`prompt`|Wenn ein interner Compilerfehler auftritt, wird ein Dialogfeld, damit Sie genauen die Daten anzeigen können, die der Compiler erfasst. Sie können bestimmen, ob vertrauliche Daten im Bericht und treffen einer Entscheidung, ob Sie diese an Microsoft gesendet. Wenn Sie senden möchten, und die Computer- und Benutzerrichtlinien dies zulassen, sendet der Compiler die Daten an Microsoft.|  
|`queue`|Den Bericht-Warteschlangen. Wenn Sie sich mit Administratorrechten anmelden, können Sie Fehler melden, seit der letzten Sie angemeldet wurden (nicht werden Sie aufgefordert, Fehlerberichte mehr als einmal alle drei Tage senden). Dies ist das Standardverhalten bei der `/errorreport` nicht angegeben wird.|  
|`send`|Wenn ein interner Compilerfehler auftritt und die Computer- und Benutzerrichtlinien dies zulassen, sendet der Compiler die Daten an Microsoft.<br /><br /> Die Option `/errorReport:send` versucht, automatisch Informationen an Microsoft gesendet. Diese Option hängt von der Registrierung ab. Weitere Informationen zum Festlegen der entsprechenden Werte in der Registrierung finden Sie unter [Aktivieren der automatischen Fehlerberichterstattung in Visual Studio 2008-Befehlszeilentools](http://go.microsoft.com/fwlink/?LinkID=184695).|  
|`none`|Wenn ein interner Compilerfehler auftritt, wird es nicht erfasst oder an Microsoft gesendet.|  
  
 Der Compiler sendet Daten, die im Stapel zum Zeitpunkt des Fehlers, der Quellcode in der Regel enthält enthält. Wenn `/errorreport` wird verwendet, mit der [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) -Option wird die gesamte Quelldatei gesendet wird.  
  
 Diese Option wird am besten verwendet, mit der [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md) option, da Microsoft-Techniker so den Fehler einfacher reproduzieren können.  
  
> [!NOTE]
>  Die `/errorreport` Option ist nicht verfügbar in der Visual Studio Development Environment; es ist nur beim Kompilieren von der Befehlszeile aus.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code versucht, kompilieren Sie `T2.vb`, und wenn der Compiler einen internen Fehler, sie werden aufgefordert, den Fehlerbericht an Microsoft zu senden.  
  
```  
vbc /errorreport:prompt t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/bugreport](../../../visual-basic/reference/command-line-compiler/bugreport.md)
