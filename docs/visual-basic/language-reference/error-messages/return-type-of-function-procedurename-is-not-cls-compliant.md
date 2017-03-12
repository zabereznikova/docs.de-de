---
title: "Return type of function &#39;&lt;procedurename&gt;&#39; is not CLS-compliant | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40027"
  - "vbc40027"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40027"
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Return type of function &#39;&lt;procedurename&gt;&#39; is not CLS-compliant
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Eine `Function`\-Prozedur ist als `<CLSCompliant(True)>` markiert, gibt jedoch einen Typ zurück, der als `<CLSCompliant(False)>` markiert, nicht markiert oder nicht geeignet ist, da er nicht kompatibel ist.  
  
 Damit eine Prozedur mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) kompatibel ist, darf sie nur CLS\-kompatible Typen verwenden.  Dies gilt für die Parametertypen, den Rückgabetyp und die Typen aller ihrer lokalen Variablen.  
  
 Die folgenden [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Datentypen sind nicht CLS\-kompatibel:  
  
-   [SByte Data Type](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong Data Type](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort Data Type](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant`\-Parameter des Attributs auf `True` oder auf `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.  Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung.  Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC40027  
  
### So beheben Sie diesen Fehler  
  
-   Wenn die `Function`\-Prozedur diesen speziellen Typ zurückgeben muss, entfernen Sie das <xref:System.CLSCompliantAttribute>.  Die Prozedur kann nicht CLS\-kompatibel sein.  
  
-   Wenn die `Function`\-Prozedur CLS\-kompatibel sein muss, ändern Sie den Rückgabetyp in den ähnlichsten CLS\-kompatiblen Typ.  Möglicherweise können Sie z. B. `Integer` anstelle von `UInteger` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.  Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long` ersetzen.  
  
-   Wenn Sie Verbindungen mit Automatisierungs\- oder COM\-Objekten verwenden, beachten Sie, dass einige Typen über andere Datenbreiten als in [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] verfügen.  Beispielsweise umfasst `int` in anderen Umgebungen oft 16 Bits.  Wenn Sie an eine solche Komponente eine 16\-Bit\-Ganzzahl zurückgeben, deklarieren Sie sie im verwalteten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Code als `Short` und nicht als `Integer`.  
  
## Siehe auch  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/de-de/4c705105-69a2-4e5e-b24e-0633bc32c7f3)