---
title: "Blitfähige und nicht blitfähige Typen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- interop marshaling, blittable types
- blittable types, interop marshaling
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: 23
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3fa97ee1df14b5e08faa944265675264c0b6d95a
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="blittable-and-non-blittable-types"></a>Blitfähige und nicht blitfähige Typen
Die meisten Datentypen verfügen über eine allgemeine Darstellung in verwaltetem und unverwaltetem Speicher und erfordern keine besondere Behandlung durch den Interop-Marshaller. Diese Typen werden *blitfähige Typen* genannt, da keine Konvertierung erforderlich ist, wenn sie zwischen verwaltetem und nicht verwaltetem Code übergeben werden.  
  
 Strukturen, die von Plattformaufrufen zurückgegeben werden, müssen blitfähige Typen sein. Der Plattformaufruf unterstützt keine nicht blitfähigen Strukturen als Rückgabetypen.  
  
 Die folgenden Typen aus dem <xref:System>-Namespace sind blitfähige Typen:  
  
-   <xref:System.Byte?displayProperty=fullName>  
  
-   <xref:System.SByte?displayProperty=fullName>  
  
-   <xref:System.Int16?displayProperty=fullName>  
  
-   <xref:System.UInt16?displayProperty=fullName>  
  
-   <xref:System.Int32?displayProperty=fullName>  
  
-   <xref:System.UInt32?displayProperty=fullName>  
  
-   <xref:System.Int64?displayProperty=fullName>  
  
-   <xref:System.UInt64?displayProperty=fullName>  
  
-   <xref:System.IntPtr?displayProperty=fullName>  
  
-   <xref:System.UIntPtr?displayProperty=fullName>  
  
-   <xref:System.Single?displayProperty=fullName>  
  
-   <xref:System.Double?displayProperty=fullName>  
  
 Die folgenden komplexen Typen sind ebenfalls blitfähige Typen:  
  
-   Eindimensionale Arrays von blitfähigen Typen, z.B. ein Array von Integern. Ein Typ, der ein Variablenarray von blitfähigen Typen enthält, ist jedoch nicht selbst blitfähig.  
  
-   Formatierte Werttypen, die ausschließlich blitfähige Typen (oder Klassen, wenn sie als formatierte Typen gemarshallt werden) enthalten. Weitere Informationen zu formatierten Werttypen finden Sie unter [Standardmäßiges Marshalling für Werttypen](http://msdn.microsoft.com/en-us/4d9a876c-e05a-40ba-bd85-bd22877f984a).  
  
 Objektverweise sind nicht für Blitvorgänge geeignet. Dies schließt ein Array von Verweisen auf Objekte ein, die selbst für Blitting geeignet sind. Beispielsweise können Sie eine Struktur definieren, die für Blitting geeignet ist, jedoch keine blitfähigen Typen, die ein Array von Verweisen auf diese Strukturen enthält.  
  
 Zur Optimierung werden Arrays von blitfähigen Typen und Klassen, die nur für Blitting geeignete Member enthalten, während des Marshalling [angeheftet](../../../docs/framework/interop/copying-and-pinning.md) und nicht kopiert. Es kann so wirken, als ob diese Typen als In/Out-Parameter gemarshallt werden, wenn der Aufrufer und der Aufgerufene im selben Apartment sind. Allerdings werden diese Typen tatsächlich als In-Parameter gemarshallt, und Sie müssen die <xref:System.Runtime.InteropServices.InAttribute>- und <xref:System.Runtime.InteropServices.OutAttribute>-Attribute anwenden, wenn Sie das Argument als In/Out-Parameter gemarshallt haben möchten.  
  
 Einige verwaltete Datentypen erfordern eine andere Darstellung in einer nicht verwalteten Umgebung. Diese nicht blitfähigen Datentypen müssen in ein Format konvertiert werden, das gemarshallt werden kann. Beispielsweise sind verwaltete Zeichenfolgen nicht blitfähige Typen, da sie in Zeichenfolgenobjekte konvertiert werden müssen, bevor sie gemarshallt werden können.  
  
 Die folgende Tabelle listet nicht blitfähige Typen aus dem <xref:System>-Namespace auf. [Delegaten](http://msdn.microsoft.com/en-us/d176ee76-f982-494b-b03d-92e4118896e2) sind Datenstrukturen, die auf eine statische Methode oder auf eine Klasseninstanz verweisen, und sind nicht blitfähig.  
  
|Nicht blitfähiger Typ|Beschreibung|  
|-------------------------|-----------------|  
|[System.Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.|  
|[System.Boolean](http://msdn.microsoft.com/en-us/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)|Konvertiert in einen 1-, 2- oder 4-Byte-Wert mit `true` als 1 oder -1.|  
|[System.Char](http://msdn.microsoft.com/en-us/cecc87c1-075e-4cde-aa56-33d189f66feb)|Konvertiert in ein Unicode- oder ANSI-Zeichen.|  
|[System.Class](http://msdn.microsoft.com/en-us/fe334af5-0123-43d8-be84-26f6f023ddb6)|Konvertiert in eine Klassenschnittstelle.|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|Konvertiert in eine Variante oder eine Schnittstelle.|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.|  
|[System.String](../../../docs/framework/interop/default-marshaling-for-strings.md)|Konvertiert in eine Zeichenfolge, die in einem NULL-Verweis oder in einem BSTR endet.|  
|[System.Valuetype](http://msdn.microsoft.com/en-us/4d9a876c-e05a-40ba-bd85-bd22877f984a)|Konvertiert in eine Struktur mit einem festen Speicherlayout.|  
|[System.Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Konvertiert in ein Array im C-Format oder ein `SAFEARRAY`.|  
  
 Klassen und Objekttypen werden nur von COM-Interop unterstützt. Informationen zu den entsprechenden Typen in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# und C++ finden Sie unter [Übersicht über die Klassenbibliothek](../../../docs/standard/class-library-overview.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Standardmäßiges Marshallingverhalten](../../../docs/framework/interop/default-marshaling-behavior.md)

