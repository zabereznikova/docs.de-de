---
title: 'Vorgehensweise: Erstellen einer C / C++-Union mit Attributen (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
ms.openlocfilehash: 0c3ebf248f5d2f20e2fff25fb8326a294b51d153
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789089"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a>Vorgehensweise: Erstellen einer C/C++-Union mit Attributen (Visual Basic)
Mithilfe von Attributen können Sie anpassen, wie Strukturen im Arbeitsspeicher angeordnet werden. Sie können z.B. das erstellen, was als eine Union in C/C++ bekannt ist, indem Sie die mit `StructLayout(LayoutKind.Explicit)`- und `FieldOffset`-Attribute verwenden.  
  
## <a name="example"></a>Beispiel  
 In diesem Codesegment beginnen alle Felder von `TestUnion` an derselben Position im Arbeitsspeicher.  
  
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
 Im Folgenden finden Sie ein weiteres Beispiel, in dem Felder an verschiedenen, explizit festgelegten Orten beginnen.  
  
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
  
 Die zwei Ganzzahlfelder `i1` und `i2` teilen die gleichen Speicheradressen wie `lg`. Diese Art der Kontrolle über das Strukturlayout ist nützlich, wenn Sie Plattformaufrufe nutzen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)
- [Attribute](../../../../standard/attributes/index.md)
- [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [Attribute (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)
- [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Erstellen benutzerdefinierter Attribute (Visual Basic))
- [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic))
