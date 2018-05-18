---
title: 'Gewusst wie: Konvertieren eines Bytearrays in einen ganzzahligen Typ (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], byte array to int
- byte arrays [C#], converting to int
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
ms.openlocfilehash: 4e8c232a604837d32675229f7f91b8e329ac4b5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-convert-a-byte-array-to-an-int-c-programming-guide"></a>Gewusst wie: Konvertieren eines Bytearrays in einen ganzzahligen Typ (C#-Programmierhandbuch)
In diesem Beispiel wird veranschaulicht, wie Sie die <xref:System.BitConverter>-Klasse dazu verwenden, einen Bytearray in einen [int](../../../csharp/language-reference/keywords/int.md)-Typ und wieder zurück in ein Bytearray zu konvertieren. Sie müssen möglicherweise Bytes in einen integrierten Datentyp konvertieren, wenn Sie z.B. Bytes aus dem Netzwerk gelesen haben. Die folgende Tabelle enthält zusätzlich zu der Methode [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) aus dem Beispiel auch die Methoden in der <xref:System.BitConverter>-Klasse, die Bytes (aus einem Bytearray) in andere integrierte Typen konvertiert.  
  
|Zurückgegebener Typ|Methode|  
|-------------------|------------|  
|`bool`|[ToBoolean(Byte\[\], Int32)](xref:System.BitConverter.ToBoolean(System.Byte[],System.Int32))|  
|`char`|[ToChar(Byte\[\], Int32)](xref:System.BitConverter.ToChar(System.Byte[],System.Int32))|  
|`double`|[ToDouble(Byte\[\], Int32)](xref:System.BitConverter.ToDouble(System.Byte[],System.Int32))|  
|`short`|[ToInt16(Byte\[\], Int32)](xref:System.BitConverter.ToInt16(System.Byte[],System.Int32))|  
|`int`|[ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32))|  
|`long`|[ToInt64(Byte\[\], Int32)](xref:System.BitConverter.ToInt64(System.Byte[],System.Int32))|  
|`float`|[ToSingle(Byte\[\], Int32)](xref:System.BitConverter.ToSingle(System.Byte[],System.Int32))|  
|`ushort`|[ToUInt16(Byte\[\], Int32)](xref:System.BitConverter.ToUInt16(System.Byte[],System.Int32))|  
|`uint`|[ToUInt32(Byte\[\], Int32)](xref:System.BitConverter.ToUInt32(System.Byte[],System.Int32))|  
|`ulong`|[ToUInt64(Byte\[\], Int32)](xref:System.BitConverter.ToUInt64(System.Byte[],System.Int32))|  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird ein Bytearray initialisiert und umgekehrt, wenn die Computerarchitektur Little-Endian entspricht (das kleinstwertige Byte wird am Anfang gespeichert). Anschließend wird die Methode [ToInt32(Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) aufgerufen, um vier Bytes im Array in einen `int` zu konvertieren. Das zweite Argument für [ToInt32 (Byte\[\], Int32)](xref:System.BitConverter.ToInt32(System.Byte[],System.Int32)) gibt den Startindex des Bytearrays an.  
  
> [!NOTE]
>  Die Ausgabe kann sich je nach der Bytereihenfolge der Architektur Ihres Computers unterscheiden.  
  
 [!code-csharp[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_1.cs)]  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Methode <xref:System.BitConverter.GetBytes%28System.Int32%29> der Klasse <xref:System.BitConverter> aufgerufen, um `int` in ein Bytearray zu konvertieren.  
  
> [!NOTE]
>  Die Ausgabe kann sich je nach der Bytereihenfolge der Architektur Ihres Computers unterscheiden.  
  
 [!code-csharp[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_2.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.BitConverter>  
 <xref:System.BitConverter.IsLittleEndian>  
 [Typen](../../../csharp/programming-guide/types/index.md)
