---
title: "Type of parameter &#39;&lt;parametername&gt;&#39; is not CLS-compliant | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc40028"
  - "bc40028"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40028"
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Type of parameter &#39;&lt;parametername&gt;&#39; is not CLS-compliant
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Prozedur ist als `<CLSCompliant(True)>` markiert, deklariert jedoch einen Parameter mit einem Typ, der als `<CLSCompliant(False)>` markiert, nicht markiert oder nicht geeignet ist, da es sich um einen nicht kompatiblen Typ handelt.  
  
 Damit eine Prozedur mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) kompatibel ist, darf sie nur CLS\-kompatible Typen verwenden.  Dies gilt für die Parametertypen, den Rückgabetyp und die Typen aller ihrer lokalen Variablen.  
  
 Die folgenden [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Datentypen sind nicht CLS\-kompatibel:  
  
-   [SByte Data Type](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong Data Type](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort Data Type](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant`\-Parameter des Attributs auf `True` oder auf `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.  Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung.  Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC40028  
  
### So beheben Sie diesen Fehler  
  
-   Wenn die Prozedur einen Parameter dieses speziellen Typs akzeptieren muss, entfernen Sie das <xref:System.CLSCompliantAttribute>.  Die Prozedur kann nicht CLS\-kompatibel sein.  
  
-   Wenn die Prozedur CLS\-kompatibel sein muss, ändern Sie den Typ dieses Parameters in den ähnlichsten CLS\-kompatiblen Typ.  Möglicherweise können Sie z. B. `Integer` anstelle von `UInteger` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.  Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long` ersetzen.  
  
-   Wenn Sie Verbindungen mit Automatisierungs\- oder COM\-Objekten verwenden, beachten Sie, dass einige Typen über andere Datenbreiten als in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen.  Beispielsweise umfasst `int` in anderen Umgebungen oft 16 Bits.  Wenn Sie eine 16\-Bit\-Ganzzahl von einer solchen Komponente akzeptieren, deklarieren Sie sie im verwalteten [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Code als `Short` und nicht als `Integer`.  
  
## Siehe auch  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/de-de/4c705105-69a2-4e5e-b24e-0633bc32c7f3)