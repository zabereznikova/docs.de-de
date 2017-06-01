---
title: "Platform Invoke Examples | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "examples [.NET Framework], platform invoke"
  - "unmanaged functions"
  - "COM interop, platform invoke"
  - "platform invoke, examples"
  - "interoperation with unmanaged code, platform invoke"
  - "DLL functions"
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Platform Invoke Examples
Die folgenden Beispiele veranschaulichen, wie Sie die **MessageBox**\-Funktion in User32.dll definieren und aufrufen können, indem Sie eine einfache Zeichenfolge als Argument übergeben.  In den Beispielen ist das [DllImportAttribute.CharSet Field](frlrfSystemRuntimeInteropServicesDllImportAttributeClassCharSetTopic)\-Feld auf **Auto** festgelegt, d. h., die Zielplattform bestimmt über die Zeichenbreite und das Marshallen von Zeichenfolgen.  
  
 Dasselbe Beispiel wird in Visual Basic, C\# und C\+\+ angezeigt.  Um alle Beispiele anzuzeigen, klicken Sie in der oberen linken Ecke der Seite auf die Schaltfläche Sprachfilter ![](../../../docs/framework/interop/media/filter2.gif "Filter2").  Weitere Beispiele finden Sie unter [Marshallen von Daten mit Plattformaufruf](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
       ByVal caption As String, ByVal Typ As Integer) As IntPtr  
End Class  
  
Public Class HelloWorld      
    Public Shared Sub Main()  
        Win32.MessageBox(0, "Hello World", "Platform Invoke Sample", 0)  
    End Sub  
End Class  
  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
     [DllImport("user32.dll", CharSet=CharSet.Auto)]  
     public static extern IntPtr MessageBox(int hWnd, String text,   
                     String caption, uint type);  
}  
  
public class HelloWorld {  
    public static void Main() {  
       Win32.MessageBox(0, "Hello World", "Platform Invoke Sample", 0);  
    }  
}  
  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" IntPtr MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
void main(void) {  
     String* pText = L"Hello World!";  
     String* pCaption = L"Platform Invoke Sample";  
     MessageBox(0, pText, pCaption, 0);  
}  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)   
 [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md)