---
title: "Ausdruck weist den Typ &quot;&lt;Typename&gt;&quot; welche einen eingeschränkten Typ und kann nicht verwendet werden, um von &quot;Object&quot; oder &quot;ValueType&quot; geerbte Member zuzugreifen | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
dev_langs:
- VB
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: aaedfd825889498159f92cbd1d615cc0064973d3
ms.lasthandoff: 03/13/2017

---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>Ausdruck weist den Typ "&lt;Typename&gt;" welche einen eingeschränkten Typ und kann nicht verwendet werden, um von 'Object' oder 'ValueType' geerbte Member zuzugreifen
Ein Ausdruck ergibt ein Typ, der von der common Language Runtime (CLR) geschachtelt werden, kann aber greift auf ein Element, das Boxing erfordert.  
  
 *Boxing* bezieht sich auf die Verarbeitung durch, die zum Konvertieren eines Typs `Object` oder in <xref:System.ValueType>.</xref:System.ValueType> Die common Language Runtime kann nicht im Feld bestimmte Typen, z. B. <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, und <xref:System.TypedReference>.</xref:System.TypedReference> </xref:System.RuntimeArgumentHandle> </xref:System.ArgIterator>  
  
 Dieser Ausdruck versucht, mit eingeschränkten Typ eine geerbte Methode aufrufen <xref:System.Object>oder <xref:System.ValueType>, z. B. <xref:System.Object.GetHashCode%2A>oder <xref:System.Object.ToString%2A>.</xref:System.Object.ToString%2A> </xref:System.Object.GetHashCode%2A> </xref:System.ValueType> </xref:System.Object> Diese Methode Zugriff auf [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] hat versucht, eine implizites Boxing-Konvertierung, die diesen Fehler verursacht.  
  
 **Fehler-ID:** BC31393  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Suchen Sie den Ausdruck, der den angegebenen Typ ergibt.  
  
2.  Suchen Sie den Teil der Anweisung, die versucht, die von <xref:System.Object>oder <xref:System.ValueType>.</xref:System.ValueType> </xref:System.Object> geerbte Methode aufzurufen  
  
3.  Schreiben Sie die Anweisung, um den Methodenaufruf zu vermeiden.  
  
## <a name="see-also"></a>Siehe auch  
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
