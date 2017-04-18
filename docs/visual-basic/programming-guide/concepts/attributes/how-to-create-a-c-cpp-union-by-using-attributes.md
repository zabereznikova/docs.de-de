---
title: 'Gewusst wie: erstellen eine C#-C++-Union mit Attributen (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ff1686328630b233b25839c79d0009d48aab5ab
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a>Gewusst wie: Erstellen einer Union in c/c++ mit Attributen (Visual Basic)
Mithilfe von Attributen können Sie anpassen, wie Strukturen im Arbeitsspeicher angeordnet werden. Sie können z. B. erstellen, eine Union in C/C++ mit sogenannten der `StructLayout(LayoutKind.Explicit)` und `FieldOffset` Attribute.  
  
## <a name="example"></a>Beispiel  
 In diesem Codesegment, alle Felder des `TestUnion` start an derselben Position im Arbeitsspeicher.  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
<System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestUnion  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public i As Integer  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public d As Double  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public c As Char  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public b As Byte  
End Structure  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden ist ein weiteres Beispiel explizit festgelegt Speicherorte, in denen Felder beginnen mit anderen.  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
 <System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestExplicit  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public lg As Long  
  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public i1 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(4)>   
     Public i2 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(8)>   
     Public d As Double  
  
     <System.Runtime.InteropServices.FieldOffset(12)>   
     Public c As Char  
  
     <System.Runtime.InteropServices.FieldOffset(14)>   
     Public b As Byte  
 End Structure  
```  
  
 Die zwei Ganzzahlfelder `i1` und `i2`, teilen die gleiche Speicheradressen als `lg`. Diese Art der Kontrolle über das Strukturlayout ist nützlich, wenn es sich bei Verwendung von Plattformaufrufen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)   
 [Attribute](https://msdn.microsoft.com/library/5x6cd29c)   
 [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Attribute (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Erstellen von benutzerdefinierten Attributen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)   
 [Zugriff auf Attribute mit Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
