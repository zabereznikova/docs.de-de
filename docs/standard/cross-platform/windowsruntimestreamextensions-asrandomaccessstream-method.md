---
title: WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
api_name: System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location: System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9057eabb7e3dfdfaa872fbcf2fe1180d0bbc7920
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a>WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream)-Methode
[Wird nur in .NET Framework 4.5.1 und neueren Versionen unterstützt]  
  
 Konvertiert den angegebenen Stream in einen Random-Access-Stream.  
  
 **Namespace:**<xref:System.IO?displayProperty=nameWithType>  
 **Assembly:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)  
  
## <a name="syntax"></a>Syntax  
  
```csharp  
[CLSCompliantAttribute(false)]  
public static  IRandomAccessStream AsRandomAccessStream(Stream stream)  
```  
  
```vb  
'Declaration  
<ExtensionAttribute> _  
<CLSCompliantAttribute(False)> _  
Public Shared Function AsRandomAccessStream ( _  
        stream As Stream) As IRandomAccessStream  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
  
 Typ: <xref:System.IO.Stream?displayProperty=nameWithType>  
Der zu konvertierende Stream.  
  
## <a name="return-value"></a>Rückgabewert  
 Typ: [Windows.Storage.Streams.RandomAccessStream](http://msdn.microsoft.com/library/windows/apps/windows.storage.streams.randomaccessstream.aspx)  
Ein [!INCLUDE[wrt](../../../includes/wrt-md.md)] random-Access-Stream, der den konvertierten Stream darstellt.  
  
## <a name="exceptions"></a>Ausnahmen  
  
|Ausnahme|Bedingung|  
|---------------|---------------|  
|<xref:System.NotSupportedException>|Der zu konvertierende Stream unterstützt keine Suchvorgänge.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Erweiterungsmethode ist nur verfügbar, wenn Sie Windows Store-Apps entwickeln. Diese Methode stellt eine komfortable Möglichkeit des Arbeitens mit Streams in Windows Store-Apps dar. Der .NET-Framework, den Sie konvertieren möchten, muss Suchvorgänge unterstützen. Weitere Informationen finden Sie unter der Methode <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
>  Diese API wird in .NET Framework 4.5.1 und neuer, aber nicht in Version 4.5 unterstützt.  
  
## <a name="version-information"></a>Versionsinformationen  
 **.NET für Windows Store-apps**  
  
 Unterstützt in: Windows 8.1  
  
## <a name="see-also"></a>Siehe auch  
 <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>--> `System.IO.WindowsRuntimeStreamExtensions`  
 [Gewusst wie: Konvertieren zwischen .NET Framework-Streams und Windows-Runtime-Streams](../../../docs/standard/io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
