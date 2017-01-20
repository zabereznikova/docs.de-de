---
title: "Gewusst wie: Konvertieren eines Bytearrays in einen ganzzahligen Typ (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Bytearrays [C#], Konvertieren in ganzzahligen Typ"
  - "Konvertierungen [C#], Bytearray in ganzzahligen Typ"
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Konvertieren eines Bytearrays in einen ganzzahligen Typ (C#-Programmierhandbuch)
In diesem Beispiel wird die <xref:System.BitConverter>\-Klasse zur Konvertierung eines Bytearrays in einen [int](../../../csharp/language-reference/keywords/int.md)\-Typ und zurück in ein Bytearray verwendet.  Sie müssen z. B. nach dem Lesen von Netzwerkbytes die Bytes in einen integrierten Datentyp konvertieren.  Neben der [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)\-Methode im Beispiel finden Sie in der folgenden Tabelle weitere Methoden in der <xref:System.BitConverter>\-Klasse zur Konvertierung von Bytes \(aus einem Bytearray\) in andere integrierte Typen.  
  
|Zurückgegebener Typ|Methode|  
|-------------------------|-------------|  
|`bool`|[ToBoolean\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToBoolean(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`char`|[ToChar\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToChar(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`double`|[ToDouble\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToDouble(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`short`|[ToInt16\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt16(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`int`|[ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`long`|[ToInt64\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt64(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`float`|[ToSingle\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToSingle(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`ushort`|[ToUInt16\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt16(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`uint`|[ToUInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`ulong`|[ToUInt64\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt64(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
  
## Beispiel  
 In diesem Beispiel wird ein Bytearray initialisiert, und das Array wird umgekehrt, falls die Computerarchitektur die Little\-Endian\-Bytefolge aufweist \(d. h., das Byte mit dem niedrigsten Wert wird zuerst gespeichert\). Dann wird die [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)\-Methode aufgerufen, um vier Bytes im Array in einen `int`\-Typ zu konvertieren.  Das zweite Argument [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) gibt den Startindex des Bytearrays an.  
  
> [!NOTE]
>  Je nach Computerarchitektur und verwendeter Endian\-Reihenfolge kann das Ergebnis vom Beispiel abweichen.  
  
 [!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array_1.cs)]  
  
## Beispiel  
 In diesem Beispiel wird die <xref:System.BitConverter.GetBytes%28System.Int32%29>\-Methode der <xref:System.BitConverter>\-Klasse aufgerufen, um einen `int`\-Typ in ein Bytearray zu konvertieren.  
  
> [!NOTE]
>  Je nach Computerarchitektur und verwendeter Endian\-Reihenfolge kann das Ergebnis vom Beispiel abweichen.  
  
 [!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array_2.cs)]  
  
## Siehe auch  
 <xref:System.BitConverter>   
 <xref:System.BitConverter.IsLittleEndian>   
 [Typen](../../../csharp/programming-guide/types/index.md)