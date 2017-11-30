---
title: 'Gewusst wie: Definieren und Verwenden von benutzerdefinierten numerischen Formatanbietern'
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
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- custom numeric format strings
- numbers [.NET Framework], custom numeric format strings
- displaying date and time data
- format providers [.NET Framework]
- custom format strings
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e44a909eb92f0d9dfa21980a918a2d370dcf427
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Gewusst wie: Definieren und Verwenden von benutzerdefinierten numerischen Formatanbietern
Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] bietet Ihnen eine umfangreiche Kontrolle über die Darstellung von numerischen Werten. Die folgenden Funktionen für die Anpassung des Formats numerischer Werte werden unterstützt:  
  
-   Standardmäßige Zahlenformatzeichenfolgen, die einen vordefinierten Satz an Formaten für die Konvertierung von Zahlen in ihre Zeichenfolgendarstellung bereitstellen. Sie verwenden können, mit einer beliebigen numerischen Formatierungsmethode, z. B. <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, mit dem eine `format` Parameter. Weitere Informationen finden Sie unter [Standard Numeric Format Strings](../../../docs/standard/base-types/standard-numeric-format-strings.md).  
  
-   Benutzerdefinierte Zahlenformatzeichenfolgen, die einen Satz von Symbolen bereitstellen, die kombiniert werden können, um benutzerdefinierte Zahlenformatbezeichner zu definieren. Sie können auch mit einer beliebigen numerischen Formatierungsmethode, z. B. verwendet <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, mit dem eine `format` Parameter. Weitere Informationen finden Sie unter [benutzerdefinierte Zahlenformatzeichenfolgen](../../../docs/standard/base-types/custom-numeric-format-strings.md).  
  
-   Benutzerdefinierte <xref:System.Globalization.CultureInfo> oder <xref:System.Globalization.NumberFormatInfo> Objekte, die die Symbole zu definieren und-Formatmustern angezeigt, die die zeichenfolgenentsprechungen von numerischen Werten verwendet. Sie verwenden können, mit einer beliebigen numerischen Formatierungsmethode, z. B. <xref:System.Int32.ToString%2A>, mit dem eine `provider` Parameter. In der Regel die `provider` Parameter wird verwendet, um kulturspezifische Formatierung angeben.  
  
 In einigen Fällen (z.B. wenn eine Anwendung eine formatierte Kontonummer, eine ID oder eine Postleitzahl anzeigen muss) sind diese drei Techniken nicht geeignet. Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] auch ermöglicht es Ihnen, ein Formatierungsobjekt definieren, der weder ein <xref:System.Globalization.CultureInfo> noch ein <xref:System.Globalization.NumberFormatInfo> Objekt, um zu bestimmen, wie ein numerischer Wert formatiert wird. Dieses Thema stellt eine Schrittanleitung für die Implementierung eines solchen Objekts bereit und bietet ein Beispiel, das Telefonnummern formatiert.  
  
### <a name="to-define-a-custom-format-provider"></a>Definieren eines benutzerdefinierten Formatanbieters  
  
1.  Definieren Sie eine Klasse, die implementiert die <xref:System.IFormatProvider> und <xref:System.ICustomFormatter> Schnittstellen.  
  
2.  Implementieren Sie die <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType>-Methode. <xref:System.IFormatProvider.GetFormat%2A>ist eine Rückrufmethode, die die Formatierungsmethode (z. B. die <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> Methode) aufruft, um das Objekt abzurufen, das tatsächlich für die Ausführung der benutzerdefinierten Formatierung zuständig ist. Eine typische Implementierung der <xref:System.IFormatProvider.GetFormat%2A> bewirkt Folgendes:  
  
    1.  Bestimmt, ob die <xref:System.Type> Objekt als eine Methode übergeben-Parameter stellt eine <xref:System.ICustomFormatter> Schnittstelle.  
  
    2.  Wenn der Parameter dar. der <xref:System.ICustomFormatter> -Schnittstelle, <xref:System.IFormatProvider.GetFormat%2A> gibt ein Objekt, das implementiert die <xref:System.ICustomFormatter> -Schnittstelle, die für die benutzerdefinierte Formatierung zuständig ist. Üblicherweise gibt das benutzerdefinierte Formatierungsobjekt sich selbst zurück.  
  
    3.  Wenn der Parameter nicht darstellt der <xref:System.ICustomFormatter> -Schnittstelle, <xref:System.IFormatProvider.GetFormat%2A> gibt `null`.  
  
3.  Implementieren Sie die <xref:System.ICustomFormatter.Format%2A>-Methode. Diese Methode wird aufgerufen, indem Sie die <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> Methode ist dafür verantwortlich, die Zeichenfolgendarstellung einer Zahl zurückzugeben. Die Implementierung der Methode umfasst üblicherweise Folgendes:  
  
    1.  Optional, stellen Sie sicher, dass die Methode legitimen zur Formatierung Dienstleistungen dient durch Untersuchen der `provider` Parameter. Zum Formatieren von Objekten, die beide implementieren <xref:System.IFormatProvider> und <xref:System.ICustomFormatter>, testen Sie dazu die `provider` Parameter für Gleichheit mit dem aktuellen Formatierungsobjekt.  
  
    2.  Bestimmen Sie, ob das Formatierungsobjekt benutzerdefinierte Formatbezeichner unterstützen soll. (Beispielsweise könnte ein Formatbezeichner „N“ angeben, dass eine US-amerikanische Telefonnummer im NANP-Format (Nordamerikanischer Nummerierungsplan) ausgegeben werden soll, und ein Bezeichner „I“ könnte eine Ausgabe im Format der ITU-T-Empfehlung E.123 angeben.) Wenn Formatbezeichner verwendet werden, muss die Methode den angegebenen Formatbezeichner verarbeiten. Übergabe an die Methode in der `format` Parameter. Wenn kein Bezeichner vorhanden ist, den Wert der `format` Parameter ist <xref:System.String.Empty?displayProperty=nameWithType>.  
  
    3.  Abrufen des numerischen Werts an die Methode als dem `arg` Parameter. Führen Sie alle Änderungen durch, die notwendig sind, um den Wert in seine Zeichenfolgendarstellung zu konvertieren.  
  
    4.  Zurückgeben der Zeichenfolgendarstellung der `arg` Parameter.  
  
### <a name="to-use-a-custom-numeric-formatting-object"></a>Verwenden eines benutzerdefinierten Zahlenformatierungsobjekts  
  
1.  Erstellen Sie eine neue Instanz der benutzerdefinierten Formatierungsklasse.  
  
2.  Rufen Sie die <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> Formatierungsmethode, und übergeben sie das benutzerdefinierte Formatierungsobjekt, den Formatbezeichner (oder <xref:System.String.Empty?displayProperty=nameWithType>, wenn eine nicht verwendet wird), und der numerische Wert, der formatiert werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert einen benutzerdefinierten Zahlenformatanbieter namens `TelephoneFormatter`, der eine Zahl, die eine US-amerikanische Telefonnummer darstellt, in das entsprechende NANP- oder E.123-Format konvertiert. Die Methode verarbeitet zwei Formatbezeichner: „N“ (zur Ausgabe des NANP-Formats) und „I“ (zur Ausgabe des internationalen E.123-Formats).  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 Der benutzerdefinierten numerischen Format-Anbieter kann verwendet werden, nur mit der <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> Methode. Der anderen Überladungen numerischen Formatierungsmethoden angeben (z. B. `ToString`), die über einen Parameter vom Typ verfügen <xref:System.IFormatProvider> nach bestehen aller der <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> Implementierung eine <xref:System.Type> Objekt, das darstellt der <xref:System.Globalization.NumberFormatInfo> Typ. Im Gegenzug sie erwarten, dass die Methode zum Zurückgeben einer <xref:System.Globalization.NumberFormatInfo> Objekt. Ist dies nicht der Fall ist, wird der benutzerdefinierten numerischen Formatanbieter ignoriert, und die <xref:System.Globalization.NumberFormatInfo> -Objekt für die aktuelle Kultur verwendet wird. Im Beispiel die `TelephoneFormatter.GetFormat` Methode verarbeitet die Möglichkeit, die nicht ordnungsgemäß in einen numerischen Wert Formatierungsmethode durch Untersuchen des Methodenparameters und das Zurückgeben von übergeben werden möglicherweise `null` , wenn es einen Typ, außer darstellt <xref:System.ICustomFormatter>.  
  
 Wenn Sie ein benutzerdefinierten numerischen Format-Anbieter einen Satz von Formatbezeichnern unterstützt, stellen Sie sicher, dass Sie ein Standardverhalten bereitstellen, wenn keine Formatbezeichner, in das Formatelement angegeben wird in verwendet das <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> -Methodenaufruf. Im Beispiel ist „N“ der Standardformatbezeichner. Dadurch kann eine Zahl in eine formatierte Telefonnummer konvertiert werden, indem ein expliziter Formatbezeichner bereitgestellt wird. Das folgende Beispiel veranschaulicht einen solchen Methodenaufruf.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 Es ermöglicht die Konvertierung aber auch, falls kein Formatbezeichner vorhanden ist. Das folgende Beispiel veranschaulicht einen solchen Methodenaufruf.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 Wenn kein Standard-Formatbezeichner definiert ist, Ihre Implementierung von der <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> -Methode einschließen sollte dem folgenden Code so, dass .NET Formatierung bereitstellen können, dass der Code nicht unterstützt.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 Bei diesem Beispiel wird die Methode, die implementiert <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> dient als eine Rückrufmethode zum dienen der <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> Methode. Aus diesem Grund untersucht die `formatProvider` Parameter, um zu bestimmen, ob es sich um einen Verweis auf die aktuelle enthält `TelephoneFormatter` Objekt. Die Methode kann jedoch auch direkt aus dem Code aufgerufen werden. In diesem Fall können Sie die `formatProvider` Parameter ermöglichen einer <xref:System.Globalization.CultureInfo> oder <xref:System.Globalization.NumberFormatInfo> -Objekt, das kulturspezifische Formatierungsinformationen bereitstellt.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kompilieren Sie den Code über csc.exe oder vb.exe in der Befehlszeile. Um den Code in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] zu kompilieren, fügen Sie ihn in eine Projektvorlage für eine Konsolenanwendung ein.  
  
## <a name="see-also"></a>Siehe auch  
 [Durchführen von Formatierungsvorgängen](../../../docs/standard/base-types/performing-formatting-operations.md)
