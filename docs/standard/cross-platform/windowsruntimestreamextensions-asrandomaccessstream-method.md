---
title: "WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream"
apilocation: 
  - "System.Runtime.WindowsRuntime.dll"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)-Methode
\[Wird nur in .NET Framework 4.5.1 und neueren Versionen unterstützt\]  
  
 Konvertiert den angegebenen Stream in einen Random\-Access\-Stream.  
  
 **Namespace:** <xref:System.IO?displayProperty=fullName>   
 **Assembly:** System.Runtime.WindowsRuntime \(in System.Runtime.WindowsRuntime.dll\)  
  
## Syntax  
  
```csharp  
[CLSCompliantAttribute(false)] public static  IRandomAccessStream AsRandomAccessStream(Stream stream)   
```  
  
```vb  
'Declaration <ExtensionAttribute> _ <CLSCompliantAttribute(False)> _ Public Shared Function AsRandomAccessStream ( _         stream As Stream) As IRandomAccessStream   
```  
  
#### Parameter  
 `stream`  
  
 Typ: <xref:System.IO.Stream?displayProperty=fullName>   
 Der zu konvertierende Stream.  
  
## Rückgabewert  
 Typ: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)   
 Ein Random\-Access\-Stream in [!INCLUDE[wrt](../../../includes/wrt-md.md)], der den konvertierten Stream darstellt.  
  
## Ausnahmen  
  
|Ausnahme|Bedingung|  
|--------------|---------------|  
|<xref:System.NotSupportedException>|Der zu konvertierende Stream unterstützt keine Suchvorgänge.|  
  
## Hinweise  
 Diese Erweiterungsmethode ist nur verfügbar, wenn Sie Windows Store\-Apps entwickeln.  Diese Methode stellt eine komfortable Möglichkeit des Arbeitens mit Streams in Windows Store\-Apps dar.  Der .NET\-Framework, den Sie konvertieren möchten, muss Suchvorgänge unterstützen.  Weitere Informationen finden Sie unter der Methode <xref:System.IO.Stream.Seek%2A?displayProperty=fullName>.  
  
> [!IMPORTANT]
>  Diese API wird in .NET Framework 4.5.1 und neuer, aber nicht in Version 4.5 unterstützt.  
  
## Versionsinformationen  
 **.NET für Windows Store\-Apps**  
  
 Unterstützt in: Windows 8.1  
  
## Siehe auch  
 <xref:System.IO.WindowsRuntimeStreamExtensions>   
 [Gewusst wie: Konvertieren zwischen .NET Framework\-Streams und Windows\-Runtime\-Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)