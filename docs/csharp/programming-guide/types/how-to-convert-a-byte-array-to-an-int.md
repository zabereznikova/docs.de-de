---
title: "Gewusst wie: Konvertieren eines Bytearrays in einen ganzzahligen Typ (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Bytearrays [C#], Konvertieren in ganzzahligen Typ"
  - "Konvertierungen [C#], Bytearray in ganzzahligen Typ"
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Gewusst wie: Konvertieren eines Bytearrays in einen ganzzahligen Typ (C#-Programmierhandbuch)
In diesem Beispiel wird die <xref:System.BitConverter>\-Klasse zur Konvertierung eines Bytearrays in einen [int](../../../csharp/language-reference/keywords/int.md)\-Typ und zurück in ein Bytearray verwendet.  Sie müssen z. B. nach dem Lesen von Netzwerkbytes die Bytes in einen integrierten Datentyp konvertieren.  Neben der [ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29>\-Methode im Beispiel finden Sie in der folgenden Tabelle weitere Methoden in der <xref:System.BitConverter>\-Klasse zur Konvertierung von Bytes \(aus einem Bytearray\) in andere integrierte Typen.  
  
|Zurückgegebener Typ|Methode|  
|-------------------------|-------------|  
|`bool`|[ToBoolean\(Byte\<xref:System.BitConverter.ToBoolean%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`char`|[ToChar\(Byte\<xref:System.BitConverter.ToChar%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`double`|[ToDouble\(Byte\<xref:System.BitConverter.ToDouble%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`short`|[ToInt16\(Byte\<xref:System.BitConverter.ToInt16%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`int`|[ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`long`|[ToInt64\(Byte\<xref:System.BitConverter.ToInt64%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`float`|[ToSingle\(Byte\<xref:System.BitConverter.ToSingle%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`ushort`|[ToUInt16\(Byte\<xref:System.BitConverter.ToUInt16%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`uint`|[ToUInt32\(Byte\<xref:System.BitConverter.ToUInt32%28System.Byte%5B%5D%2CSystem.Int32%29>|  
|`ulong`|[ToUInt64\(Byte\<xref:System.BitConverter.ToUInt64%28System.Byte%5B%5D%2CSystem.Int32%29>|  
  
## Beispiel  
 In diesem Beispiel wird ein Bytearray initialisiert, und das Array wird umgekehrt, falls die Computerarchitektur die Little\-Endian\-Bytefolge aufweist \(d. h., das Byte mit dem niedrigsten Wert wird zuerst gespeichert\). Dann wird die [ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29>\-Methode aufgerufen, um vier Bytes im Array in einen `int`\-Typ zu konvertieren.  Das zweite Argument [ToInt32\(Byte\<xref:System.BitConverter.ToInt32%28System.Byte%5B%5D%2CSystem.Int32%29> gibt den Startindex des Bytearrays an.  
  
> [!NOTE]
>  Je nach Computerarchitektur und verwendeter Endian\-Reihenfolge kann das Ergebnis vom Beispiel abweichen.  
  
 [!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-byte-ar_1.cs)]  
  
## Beispiel  
 In diesem Beispiel wird die <xref:System.BitConverter.GetBytes%28System.Int32%29>\-Methode der <xref:System.BitConverter>\-Klasse aufgerufen, um einen `int`\-Typ in ein Bytearray zu konvertieren.  
  
> [!NOTE]
>  Je nach Computerarchitektur und verwendeter Endian\-Reihenfolge kann das Ergebnis vom Beispiel abweichen.  
  
 [!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-a-byte-ar_2.cs)]  
  
## Siehe auch  
 <xref:System.BitConverter>   
 <xref:System.BitConverter.IsLittleEndian>   
 [Typen](../../../csharp/programming-guide/types/index.md)