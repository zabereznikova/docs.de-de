---
title: "Blittable and Non-Blittable Types | Microsoft Docs"
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
  - "interop marshaling, blittable types"
  - "blittable types, interop marshaling"
ms.assetid: d03b050e-2916-49a0-99ba-f19316e5c1b3
caps.latest.revision: 23
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 23
---
# Blittable and Non-Blittable Types
Die meisten Datentypen verfügen über gemeinsame Darstellungen im verwalteten und im nicht verwalteten Speicher. Für sie ist keine Sonderbehandlung durch den Interop\-Marshaller erforderlich.  Sie werden als *blitfähige Typen* bezeichnet, da sie bei der Übergabe von verwaltetem an nicht verwalteten Code nicht umgewandelt werden müssen.  
  
 Strukturen, die von Plattformaufrufen zurückgegeben werden, müssen blitfähige Typen sein.  Nicht blitfähige Strukturen werden als Rückgabetypen für Plattformaufrufe nicht unterstützt.  
  
 Bei folgenden Typen aus dem <xref:System>\-Namespace handelt es sich um blitfähige Typen:  
  
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
  
 Außerdem sind auch die folgenden komplexen Typen blitfähige Typen:  
  
-   Eindimensionale Arrays von blitfähigen Typen, z. B. Arrays von ganzen Zahlen.  Ein Typ, der ein variables Array blitfähiger Typen enthält, ist jedoch nicht selbst blitfähig.  
  
-   Formatierte Werttypen, die ausschließlich blitfähige Typen enthalten \(und Klassen, wenn diese als formatierte Typen gemarshallt wurden\).  Weitere Informationen zu formatierten Werttypen finden Sie unter [Default Marshaling for Value Types](http://msdn.microsoft.com/de-de/4d9a876c-e05a-40ba-bd85-bd22877f984a).  
  
 Objektverweise sind nicht blitfähig.  Dies schließt ein Array von Verweisen auf Objekte ein, die selbst blitfähig sind.  Es ist zum Beispiel möglich, eine Struktur zu definieren, die blitfähig ist, jedoch können Sie keinen blitfähigen Typen definieren, der ein Array von Verweisen auf diese Strukturen enthält.  
  
 Zur Optimierung werden Arrays von blitfähigen Typen und Klassen, die ausschließlich blitfähige Member enthalten, nicht während des Marshallens kopiert, sondern [fixiert](../../../docs/framework/interop/copying-and-pinning.md).  Wenn Aufrufer und Aufgerufener sich in demselben Apartment befinden, kann es den Anschein haben, dass diese Typen als In\/Out\-Parameter gemarshallt werden.  Tatsächlich werden diese Typen jedoch als In\-Parameter gemarshallt. Um das Argument als In\/Out\-Parameter zu marshallen, müssen Sie daher das <xref:System.Runtime.InteropServices.InAttribute>\-Attribut und das <xref:System.Runtime.InteropServices.OutAttribute>\-Attribut anwenden.  
  
 Einige verwaltete Datentypen erfordern eine andere Darstellung in einer nicht verwalteten Umgebung.  Diese nicht blitfähige Datentypen müssen in ein Formular konvertiert werden, das gemarshallt werden kann.  Bei verwalteten Zeichenfolgen handelt es sich zum Beispiel um nicht blitfähige Typen, da sie in Zeichenfolgenobjekte konvertiert werden müssen, bevor sie gemarschallt werden können.  
  
 In der folgenden Tabelle werden nicht blitfähige Typen aus dem <xref:System>\-Namespace aufgelistet.  [Delegaten](http://msdn.microsoft.com/de-de/d176ee76-f982-494b-b03d-92e4118896e2), d. h. Datenstrukturen, die auf eine **static**\-Methode oder eine Klasseninstanz verweisen, sind ebenfalls nicht blitfähig.  
  
|Nicht blitfähiger Typ|Beschreibung|  
|---------------------------|------------------|  
|[System.Array](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Wird in ein Array im C\-Format oder ein `SAFEARRAY` umgewandelt.|  
|[System.Boolean](http://msdn.microsoft.com/de-de/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)|Wird in einen Wert mit 1, 2 oder 4 Bytes mit `true` als 1 oder –1 konvertiert.|  
|[System.Char](http://msdn.microsoft.com/de-de/cecc87c1-075e-4cde-aa56-33d189f66feb)|Wird in ein Unicode\- oder ANSI\-Zeichen umgewandelt.|  
|[System.Class](http://msdn.microsoft.com/de-de/fe334af5-0123-43d8-be84-26f6f023ddb6)|Wird in eine Klassenschnittstelle umgewandelt.|  
|[System.Object](../../../docs/framework/interop/default-marshaling-for-objects.md)|Wird in eine Variante oder Schnittstelle umgewandelt.|  
|[System.Mdarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Wird in ein Array im C\-Format oder ein `SAFEARRAY` umgewandelt.|  
|[System.String](../../../docs/framework/interop/default-marshaling-for-strings.md)|Wird in BSTR oder in eine Zeichenfolge konvertiert, die in einem Nullverweis endet.|  
|[System.Valuetype](http://msdn.microsoft.com/de-de/4d9a876c-e05a-40ba-bd85-bd22877f984a)|Wird in eine Struktur mit einem festen Speicherlayout umgewandelt.|  
|[System.Szarray](../../../docs/framework/interop/default-marshaling-for-arrays.md)|Wird in ein Array im C\-Format oder ein `SAFEARRAY` umgewandelt.|  
  
 Klassen und Objekttypen werden nur von COM\-Interop unterstützt.  Informationen zu entsprechenden Typen in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C\# und C\+\+ finden Sie unter [Übersicht über die Klassenbibliothek](../../../docs/standard/class-library-overview.md).  
  
## Siehe auch  
 [Default Marshaling Behavior](../../../docs/framework/interop/default-marshaling-behavior.md)