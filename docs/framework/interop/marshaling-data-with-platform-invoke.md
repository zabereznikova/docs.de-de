---
title: "Marshaling Data with Platform Invoke | Microsoft Docs"
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
  - "platform invoke, marshaling data"
  - "data marshaling, platform invoke"
  - "marshaling, platform invoke"
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Marshaling Data with Platform Invoke
Zum Aufrufen von Funktionen, die aus einer unverwalteten Bibliothek exportiert wurden, erfordert eine .NET Framework\-Anwendung einen Funktionsprototypen im verwalteten Code, der die unverwaltete Funktion darstellt.  Gehen Sie zum Erstellen eines Prototypen, der den Aufruf der Plattform für das korrekte Marshalling von Daten ermöglicht, gehen Sie folgendermaßen vor:  
  
-   Wenden Sie das [DLLImportAttribute](frlrfSystemRuntimeInteropServicesDllImportAttributeClassTopic)\-Attribut auf die statische Funktion oder Methode im verwalteten Code an.  
  
-   Ersetzen Sie verwaltete Datentypen durch unverwaltete Datentypen.  
  
 Sie können die mit einer unverwalteten Funktion bereitgestellten Dokumentation verwendet, um einen äquivalenten verwalteten Prototypen zu erstellen, indem Sie das Attribut mit seinen optionalen Feldern anwenden und verwaltete Datentypen durch unverwaltete Datentypen ersetzen.  Anweisungen zum Anwenden von **DllImportAttribute** finden Sie unter [Verwenden nicht verwalteter DLL\-Funktionen](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).  
  
 Dieser Abschnitt enthält Beispiele, die zeigen, wie Prototypen für verwaltete Funktionen erstellt werden, an die Argumente übergeben und von denen Werte von Funktionen zurückgegeben werden, die aus unverwalteten Bibliotheken exportiert wurden.  Die Beispiele zeigen auch, wann das <xref:System.Runtime.InteropServices.MarshalAsAttribute>\-Attribut und die <xref:System.Runtime.InteropServices.Marshal>\-Klasse zum expliziten Marshallen von Daten verwendet werden.  
  
## Datentypen für den Plattformaufruf  
 Die folgende Tabelle listet die Datentypen auf, die in der WIN 32\-API \(aufgeführt in Wtypes.h\) verwendet werden, und die Funktionen im C\-Stil auf.  Viele unverwaltete Bibliotheken enthalten Funktionen, die diese Datentypen als Parameter und Rückgabewerte übergeben.  Die dritte Spalte enthält den entsprechenden in .NET Framework integrierten Werttype oder die Klasse, die Sie in verwaltetem Code verwenden.  In einigen Fällen können Sie einen Typ der gleichen Größe durch den in der Tabelle aufgeführten Typ ersetzen.  
  
|Unverwalteter Typ in Wtypes.h|Unverwalteter Typ in C\-Sprache|Name der verwalteten Klasse|Beschreibung|  
|-----------------------------------|-------------------------------------|---------------------------------|------------------|  
|**HANDLE**|**void\***|<xref:System.IntPtr?displayProperty=fullName>|32 Bit unter 32\-Bit\-Windows\-Betriebssystemen, 64 Bit unter 64\-Bit\-Windows\-Betriebssystemen.|  
|**BYTE**|**unsigned char**|<xref:System.Byte?displayProperty=fullName>|8 Bit|  
|**SHORT**|**short**|<xref:System.Int16?displayProperty=fullName>|16 Bit|  
|**WORD**|**unsigned short**|<xref:System.UInt16?displayProperty=fullName>|16 Bit|  
|**INT**|**int**|<xref:System.Int32?displayProperty=fullName>|32 Bit|  
|**UINT**|**unsigned int**|<xref:System.UInt32?displayProperty=fullName>|32 Bit|  
|**LONG**|**long**|<xref:System.Int32?displayProperty=fullName>|32 Bit|  
|**BOOL**|**long**|[\<caps:sentence id\="tgt48" sentenceid\="f5f846452032b75e5fcec49a05fe125a" class\="tgtSentence"\>System.Int32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|32 Bit|  
|**DWORD**|**unsigned long**|<xref:System.UInt32?displayProperty=fullName>|32 Bit|  
|**ULONG**|**unsigned long**|<xref:System.UInt32?displayProperty=fullName>|32 Bit|  
|**CHAR**|**char**|<xref:System.Char?displayProperty=fullName>|Mit ANSI ergänzen.|  
|**WCHAR**|**wchar\_t**|<xref:System.Char?displayProperty=fullName>|Mit Unicode ergänzen.|  
|**LPSTR**|**char\***|<xref:System.String?displayProperty=fullName> oder <xref:System.Text.StringBuilder?displayProperty=fullName>|Mit ANSI ergänzen.|  
|**LPCSTR**|**Const char\***|<xref:System.String?displayProperty=fullName> oder <xref:System.Text.StringBuilder?displayProperty=fullName>|Mit ANSI ergänzen.|  
|**LPWSTR**|**wchar\_t\***|<xref:System.String?displayProperty=fullName> oder <xref:System.Text.StringBuilder?displayProperty=fullName>|Mit Unicode ergänzen.|  
|**LPCWSTR**|**Const wchar\_t\***|<xref:System.String?displayProperty=fullName> oder <xref:System.Text.StringBuilder?displayProperty=fullName>|Mit Unicode ergänzen.|  
|**FLOAT**|**Float**|<xref:System.Single?displayProperty=fullName>|32 Bit|  
|**DOUBLE**|**Double**|<xref:System.Double?displayProperty=fullName>|64 Bit|  
  
 Informationen zu den entsprechenden Typen in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# und C\+\+ finden Sie unter [Einführung in die .NET Framework\-Klassenbibliothek](../../../docs/standard/class-library-overview.md).  
  
## PinvokeLib.dll  
 Mit dem folgenden Code werden die Bibliotheksfunktionen definiert, die von der Pinvoke.dll bereitgestellt werden.  Viele Beispiele in diesem Abschnitt rufen diese Bibliothek auf.  
  
### Beispiel  
 [!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]  
  
 [!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]