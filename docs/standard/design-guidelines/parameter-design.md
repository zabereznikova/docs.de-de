---
title: Parameterentwurf
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d49c4263517830f46b1416684c7d9b874cda4db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="parameter-design"></a>Parameterentwurf
Dieser Abschnitt enthält allgemeine Richtlinien für Parameter Entwurf, einschließlich Abschnitte mit Richtlinien für die Überprüfung der Argumente. Sie sollten darüber hinaus finden Sie in der beschriebenen Richtlinien [Benennung von Parametern](../../../docs/standard/design-guidelines/naming-parameters.md).  
  
 **Führen Sie ✓** verwenden, der am wenigsten abgeleiteten Parametertyp, die die Funktionen für das Element bereitstellt.  
  
 Nehmen Sie beispielsweise an, dass eine Methode zu entwerfen, die listet und jedes Element in der Konsole ausgegeben, werden sollen. Eine solche Methode ergreift <xref:System.Collections.IEnumerable> als Parameter nicht <xref:System.Collections.ArrayList> oder <xref:System.Collections.IList>, z. B..  
  
 **X nicht** reservierte Parameter verwenden.  
  
 Wenn weitere Eingabe für ein Element in einer künftigen Version erforderlich ist, kann eine neue Überladung hinzugefügt werden.  
  
 **X nicht** haben öffentlich verfügbar gemachten Methoden, die Zeiger, Arrays von Zeigern oder mehrdimensionale Arrays als Parameter akzeptieren.  
  
 Zeiger und mehrdimensionale Arrays sind relativ schwer, ordnungsgemäß zu verwenden. In fast allen Fällen können APIs neu gestaltet werden, um zu vermeiden, diese Typen als Parameter übernimmt.  
  
 **✓ FÜHREN** platzieren Sie alle `out` Parameter, die alle per-Wert und `ref` Parameter (ausgenommen Parameterarrays), auch wenn dies zu einer Inkonsistenz der Sortierung zwischen Überladungen Parameter führt (finden Sie unter [Member Überladen von](../../../docs/standard/design-guidelines/member-overloading.md)).  
  
 Die `out` Parameter können als zusätzliche Werte angezeigt werden, und gruppieren sie macht die Signatur der Methode leichter zu verstehen.  
  
 **Führen Sie ✓** benennen Parameter aus, wenn Sie Member überschreiben oder Implementieren von Schnittstellenmembern konsistent sein.  
  
 Dies kommuniziert besser die Beziehung zwischen den Methoden.  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a>Auswählen zwischen Enum und booleschen Parametern  
 **Führen Sie ✓** Enumerationen verwenden, wenn ein Element mindestens zwei boolesche Parameter hätten.  
  
 **X nicht** boolesche Werte verwenden, es sei denn, Sie absolut sicher, dass es werden nie mehr als zwei Werte erforderlich sind.  
  
 Enumerationen bieten Ihnen einige Platz für zukünftige Werte hinzufügen, aber Sie sollten alle verbundenen Auswirkungen auf den zum Hinzufügen von Werten für Enumerationen, die in beschrieben werden [Enum-Entwurf](../../../docs/standard/design-guidelines/enum.md).  
  
 **✓ GGF.** mit boolesche Werte für Konstruktorparameter, die tatsächlich zwei-Status-Werte sind und zur Initialisierung von boolescher Eigenschaften, die einfach verwendet werden.  
  
### <a name="validating-arguments"></a>Überprüfen von Argumenten  
 **Führen Sie ✓** weitergegebenen Argumenten um öffentlich, geschützt oder explizit implementierten Member zu überprüfen. Löst <xref:System.ArgumentException?displayProperty=nameWithType>, oder eine ihrer Unterklassen, wenn die Validierung fehlschlägt.  
  
 Beachten Sie, dass die tatsächliche Validierung nicht unbedingt in der öffentlichen oder geschützten Member selbst durchgeführt werden soll. Dies kann auf einer niedrigeren Ebene in eine private oder interne Routine eintreten. Im Mittelpunkt ist, überprüft die Argumente, die gesamte Oberfläche, die den Endbenutzern zur Verfügung gestellt wird.  
  
 **Führen Sie ✓** auslösen <xref:System.ArgumentNullException> Wenn ein null-Argument übergeben wird und das Element keine null-Argumente unterstützt.  
  
 **Führen Sie ✓** Enum-Parameter überprüft.  
  
 Führen Sie Sie nicht davon gehen Sie aus, dass die Enum-Argumente in den Bereich, der durch die Enumeration definiert werden. Die CLR ermöglicht es, einen ganzzahligen Wert in einen Enum-Wert umwandeln, selbst wenn der Wert nicht in der Enumeration definiert ist.  
  
 **X nicht** verwenden <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> für Enum Bereich überprüft.  
  
 **Führen Sie ✓** Beachten Sie, dass änderbare Argumente möglicherweise geändert wurden, nachdem sie überprüft wurden.  
  
 Wenn der Member sicherheitsrelevant ist, werden Sie aufgefordert, erstellen Sie eine Kopie, und klicken Sie dann zu überprüfen und verarbeiten das Argument.  
  
### <a name="parameter-passing"></a>Parameterübergabe  
 Aus der Perspektive eines Designers Framework, es gibt drei Hauptgruppen von Parametern: per-Wert-Parametern, `ref` Parameter, und `out` Parameter.  
  
 Wenn ein Argument durch einen Parameter nach Wert übergeben wird, erhält das Element eine Kopie des tatsächlichen Arguments übergeben. Wenn das Argument ein Werttyp ist, wird eine Kopie des Arguments auf dem Stapel abgelegt. Wenn das Argument ein Verweistyp ist, wird eine Kopie des Verweises auf dem Stapel abgelegt. Am häufigsten verwendete CLR-Sprachen wie c#, VB.NET und C++-Standard zum Übergeben von Parametern durch einen Wert.  
  
 Wenn ein Argument übergeben wird, über eine `ref` Parameter, das Element erhält einen Verweis auf das tatsächliche Argument übergeben. Wenn das Argument ein Werttyp ist, wird ein Verweis auf das Argument auf dem Stapel abgelegt. Wenn das Argument ein Verweistyp ist, wird ein Verweis auf den Verweis auf dem Stapel abgelegt. `Ref`Parameter können verwendet werden, um das Element so ändern Sie die vom Aufrufer übergegebene Argumente zu ermöglichen.  
  
 `Out`Parameter sind ähnlich `ref` Parameter, mit einige geringfügige Unterschiede. Der Parameter ist anfänglich betrachtet werden, nicht zugewiesen und kann im Hauptteil Elements gelesen werden, bevor ihr einen Wert zugewiesen wird. Außerdem muss der Parameter einen Wert zugewiesen werden, bevor das Element zurückgibt.  
  
 **X vermeiden** mit `out` oder `ref` Parameter.  
  
 Mit `out` oder `ref` Parameter erfordert Erfahrung mit Zeigern, Kenntnisse der Unterschiede zwischen Wert- und Verweistypen und Arbeiten mit Methoden mit mehreren Rückgabewerten. Außerdem ist der Unterschied zwischen `out` und `ref` Parameter wird nicht umfassend unterstützt. Framework Architekten Entwerfen für eine Breite Zielgruppe sollten nicht erwarten, dass der Benutzer mit `out` oder `ref` Parameter.  
  
 **X nicht** Verweistypen als Verweis übergeben.  
  
 Es gibt einige wenige Ausnahmen für die Regel ein, z. B. eine Methode, die zum Austauschen von Verweise verwendet werden kann.  
  
### <a name="members-with-variable-number-of-parameters"></a>Elemente mit einer Variablen Anzahl von Parametern  
 Elemente, die eine Variable Anzahl von Argumenten akzeptieren können, werden durch die Bereitstellung eines Arrayparameter ausgedrückt. Beispielsweise <xref:System.String> bietet die folgende Methode:  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 Ein Benutzer kann dann rufen Sie die <xref:System.String.Format%2A?displayProperty=nameWithType> -Methode wie folgt:  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 Hinzufügen des Params-Schlüsselworts in c# auf einen Arrayparameter ändert der Parameter auf einen so genannten Params-Arrayparameter und verfügt über eine Tastenkombination erstellen Sie ein temporäres Array.  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 Auf diese Weise können die Benutzer zum Aufrufen der Methode durch die Elemente des Arrays direkt in der Argumentliste übergeben.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 Beachten Sie, dass der Params-Schlüsselworts nur der letzte Parameter in der Parameterliste hinzugefügt werden kann.  
  
 **✓ GGF.** Arrayparameter des Params-Schlüsselworts hinzugefügt, wenn Sie davon ausgehen, die Endbenutzer zum Übergeben von Arrays mit einer kleinen Anzahl von Elementen dass. Wenn davon ausgegangen wird, dass viele Elemente gemeinsam Szenarien übergeben werden, Benutzer übergibt diese Elemente Inline wahrscheinlich nicht trotzdem und des Params-Schlüsselworts ist daher nicht erforderlich.  
  
 **X vermeiden** Params-Arrays verwenden, wenn ein Aufrufer fast immer die Eingabe bereits in einem Array würde.  
  
 Mitglieder mit Arrayparametern Byte würde z. B. durch Übergeben der einzelnen Bytes fast nie aufgerufen werden. Aus diesem Grund verwenden Sie Byte Arrayparametern in .NET Framework nicht des Params-Schlüsselworts.  
  
 **X nicht** Params-Arrays verwenden, wenn das Array vom dauert des Params-Array Parameters-Element geändert wird.  
  
 Aufgrund der Tatsache, dass viele Compiler die Argumente für das Element in ein temporäres Array an der Aufrufsite verwandeln, das Array kann kein temporäres Objekt sein, und daher keine Änderungen an das Array verloren.  
  
 **✓ GGF.** des Params-Schlüsselworts in einer einfachen Überladung verwenden, auch wenn eine komplexere Überladung, konnte ihn nicht verwenden.  
  
 Fragen Sie sich, wenn Benutzer das Parameterarray in einer Überladung müssen, auch wenn es in alle Überladungen wurden keine Wert würde.  
  
 **Führen Sie ✓** versuchen, Order-Parameter, und es Ihnen ermöglicht mithilfe des Params-Schlüsselworts.  
  
 **✓ GGF.** spezielle Überladungen und Codepfade für Aufrufe mit einer kleinen Anzahl von Argumenten in extrem leistungsabhängigen-APIs bereitstellen.  
  
 Dadurch möglich, vermeiden Sie das Array von Objekten erstellen, wenn die API mit einer kleinen Anzahl von Argumenten aufgerufen wird. Bilden Sie die Namen der Parameter ein Singularform des Arrayparameter und sowie ein numerisches Suffix hinzugefügt.  
  
 Sie sollten dies nur tun, wenn Sie beabsichtigen, um Sonderfällen der gesamte Codepfad, erstellen Sie nicht nur ein Array und rufen Sie die allgemeine Methode.  
  
 **Führen Sie ✓** Beachten Sie, dass Null kann als ein Params-Argument übergeben werden.  
  
 Sie sollten überprüfen, dass das Array nicht vor der Verarbeitung null ist.  
  
 **X nicht** verwenden die `varargs` Methoden, sogenannten mit den Auslassungspunkten.  
  
 Einige CLR-Sprachen, z. B. C++, unterstützen eine alternative Konvention für die Übergabe von Variablen Parameterlisten aufgerufen `varargs` Methoden. Die Konvention sollte nicht in Frameworks verwendet werden, da sie nicht CLS-kompatibel ist.  
  
### <a name="pointer-parameters"></a>Zeigerparameter  
 Im Allgemeinen Zeiger nicht in den öffentlichen Oberflächenbereich ein Framework ausgereifte verwalteten Code angezeigt werden soll. In den meisten Fällen, sollte als Zeiger gekapselt werden. Jedoch in einigen Fällen Zeiger aus Gründen der Interoperabilität erforderlich sind, und Verwendung von Zeigern in solchen Fällen ist geeignet.  
  
 **Führen Sie ✓** bieten eine Alternative für ein Element, das ein Zeigerargument akzeptiert, da Zeiger nicht CLS-kompatibel sind.  
  
 **X vermeiden** auf diese Weise die aufwändige Prüfung von Zeigerargumente Argument.  
  
 **Führen Sie ✓** Konventionen gemeinsamen Zeiger-bezogene beim Entwerfen der Member mit Zeigern.  
  
 Beispielsweise besteht keine Notwendigkeit, übergeben den Startindex, da einfache Zeigerarithmetik verwendet werden kann, um das gleiche Ergebnis zu erreichen.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
