---
title: Blitfähige und nicht blitfähige Typen
ms.date: 03/30/2017
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
ms.openlocfilehash: 816b854120f09efef69bd8ceb2d3650e5a8e7af0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123734"
---
# <a name="blittable-and-non-blittable-types"></a>Blitfähige und nicht blitfähige Typen
Die meisten Datentypen verfügen über eine allgemeine Darstellung in verwaltetem und unverwaltetem Speicher und erfordern keine besondere Behandlung durch den Interop-Marshaller. Diese Typen werden *blitfähige Typen* genannt, da keine Konvertierung erforderlich ist, wenn sie zwischen verwaltetem und nicht verwaltetem Code übergeben werden.  
  
 Strukturen, die von Plattformaufrufen zurückgegeben werden, müssen blitfähige Typen sein. Der Plattformaufruf unterstützt keine nicht blitfähigen Strukturen als Rückgabetypen.  
  
 Die folgenden Typen aus dem <xref:System>-Namespace sind blitfähige Typen:  
  
- <xref:System.Byte?displayProperty=nameWithType>  
  
- <xref:System.SByte?displayProperty=nameWithType>  
  
- <xref:System.Int16?displayProperty=nameWithType>  
  
- <xref:System.UInt16?displayProperty=nameWithType>  
  
- <xref:System.Int32?displayProperty=nameWithType>  
  
- <xref:System.UInt32?displayProperty=nameWithType>  
  
- <xref:System.Int64?displayProperty=nameWithType>  
  
- <xref:System.UInt64?displayProperty=nameWithType>  
  
- <xref:System.IntPtr?displayProperty=nameWithType>  
  
- <xref:System.UIntPtr?displayProperty=nameWithType>  
  
- <xref:System.Single?displayProperty=nameWithType>  
  
- <xref:System.Double?displayProperty=nameWithType>  
  
 Die folgenden komplexen Typen sind ebenfalls blitfähige Typen:  
  
- Eindimensionale Arrays von blitfähigen Typen, z.B. ein Array von Integern. Ein Typ, der ein Variablenarray von blitfähigen Typen enthält, ist jedoch nicht selbst blitfähig.  
  
- Formatierte Werttypen, die ausschließlich blitfähige Typen (oder Klassen, wenn sie als formatierte Typen gemarshallt werden) enthalten. Weitere Informationen zu formatierten Werttypen finden Sie unter [Standardmäßiges Marshalling für Werttypen](default-marshaling-behavior.md#default-marshaling-for-value-types).  
  
 Objektverweise sind nicht für Blitvorgänge geeignet. Dies schließt ein Array von Verweisen auf Objekte ein, die selbst für Blitting geeignet sind. Beispielsweise können Sie eine Struktur definieren, die für Blitting geeignet ist, jedoch keine blitfähigen Typen, die ein Array von Verweisen auf diese Strukturen enthält.  
  
 Zur Optimierung werden Arrays von blitfähigen Typen und Klassen, die nur für Blitting geeignete Member enthalten, während des Marshalling [angeheftet](copying-and-pinning.md) und nicht kopiert. Es kann so wirken, als ob diese Typen als In/Out-Parameter gemarshallt werden, wenn der Aufrufer und der Aufgerufene im selben Apartment sind. Allerdings werden diese Typen tatsächlich als In-Parameter gemarshallt, und Sie müssen die <xref:System.Runtime.InteropServices.InAttribute>- und <xref:System.Runtime.InteropServices.OutAttribute>-Attribute anwenden, wenn Sie das Argument als In/Out-Parameter gemarshallt haben möchten.  
  
 Einige verwaltete Datentypen erfordern eine andere Darstellung in einer nicht verwalteten Umgebung. Diese nicht blitfähigen Datentypen müssen in ein Format konvertiert werden, das gemarshallt werden kann. Beispielsweise sind verwaltete Zeichenfolgen nicht blitfähige Typen, da sie in Zeichenfolgenobjekte konvertiert werden müssen, bevor sie gemarshallt werden können.  
  
 Die folgende Tabelle listet nicht blitfähige Typen aus dem <xref:System>-Namespace auf. [Delegaten](default-marshaling-behavior.md#default-marshaling-for-delegates) sind Datenstrukturen, die auf eine statische Methode oder auf eine Klasseninstanz verweisen, und sind nicht blitfähig.  
  
|Nicht blitfähiger Typ|Beschreibung|  
|-------------------------|-----------------|  
|[System.Array](default-marshaling-for-arrays.md)|Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.|  
|[System.Boolean](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/t2t3725f(v=vs.100))|Konvertiert in einen 1-, 2- oder 4-Byte-Wert mit `true` als 1 oder -1.|  
|[System.Char](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/6tyybbf2(v=vs.100))|Konvertiert in ein Unicode- oder ANSI-Zeichen.|  
|[System.Class](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/s0968xy8(v=vs.100))|Konvertiert in eine Klassenschnittstelle.|  
|[System.Object](default-marshaling-for-objects.md)|Konvertiert in eine Variante oder eine Schnittstelle.|  
|[System.Mdarray](default-marshaling-for-arrays.md)|Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.|  
|[System.String](default-marshaling-for-strings.md)|Konvertiert in eine Zeichenfolge, die in einem NULL-Verweis oder in einem BSTR endet.|  
|[System.Valuetype](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0t2cwe11(v=vs.100))|Konvertiert in eine Struktur mit einem festen Speicherlayout.|  
|[System.Szarray](default-marshaling-for-arrays.md)|Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.|  
  
 Klassen und Objekttypen werden nur von COM-Interop unterstützt. Informationen zu den entsprechenden Typen in Visual Basic, C# und C++ finden Sie unter [Übersicht über die Klassenbibliothek](../../standard/class-library-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)](default-marshaling-behavior.md)
