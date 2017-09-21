---
title: Migrieren der Windows Store-App auf .NET Native
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
caps.latest.revision: 29
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 55414d4479ca3cca8a7b5fbb15e4982b5dd12aad
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="migrating-your-windows-store-app-to-net-native"></a>Migrieren der Windows Store-App auf .NET Native
[!INCLUDE[net_native](../../../includes/net-native-md.md)] stellt eine statische Kompilierung von Anwendungen im Windows Store oder auf dem Computer des Entwicklers bereit. Dies unterscheidet sich von der dynamischen Kompilierung für Windows Store-Apps durch den JIT-Compiler (Just-in-Time) oder den [Native Image Generator (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) auf dem Gerät. Trotz der Unterschiede versucht [!INCLUDE[net_native](../../../includes/net-native-md.md)] , die Kompatibilität mit den [.NET für Windows Store-Apps](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)beizubehalten. Zum größten Teil funktioniert das, was für die .NET für Windows Store-Apps funktioniert, auch für [!INCLUDE[net_native](../../../includes/net-native-md.md)].  In einigen Fällen können jedoch Verhaltensänderungen auftreten. Dieses Dokument erläutert die Unterschiede zwischen den standardmäßigen .NET für Windows Store-Apps und [!INCLUDE[net_native](../../../includes/net-native-md.md)] in den folgenden Bereichen:  
  
-   [Allgemeine Laufzeitunterschiede](#Runtime)  
  
-   [Dynamische Programmierunterschiede](#Dynamic)  
  
-   [Andere Unterschiede im Zusammenhang mit Reflektion](#Reflection)  
  
-   [Nicht unterstützte Szenarios und APIs](#Unsupported)  
  
-   [Visual Studio-Unterschiede](#VS)  
  
<a name="Runtime"></a>   
## <a name="general-runtime-differences"></a>Allgemeine Laufzeitunterschiede  
  
-   Ausnahmen wie <xref:System.TypeLoadException>, die vom JIT-Compiler ausgelöst werden, wenn eine Anwendung auf der Common Language Runtime (CLR) ausgeführt wird, resultieren in der Regel in Fehlern während der Kompilierung, wenn die Verarbeitung durch [!INCLUDE[net_native](../../../includes/net-native-md.md)]erfolgt.  
  
-   Rufen Sie die <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=fullName> -Methode nicht vom UI-Thread einer Anwendung auf. Dies kann zu einem Deadlock für [!INCLUDE[net_native](../../../includes/net-native-md.md)]führen.  
  
-   Verlassen Sie sich nicht auf die Aufrufreihenfolge des statischen Klassenkonstruktors. In [!INCLUDE[net_native](../../../includes/net-native-md.md)]unterscheidet sich die Aufrufreihenfolge von der Reihenfolge in der Standardlaufzeit. (Auch mit der Standardlaufzeit sollten Sie sich nicht auf die Reihenfolge der Ausführung der statischen Klassenkonstruktoren verlassen.)  
  
-   Endlosschleifen ohne einen Anruf (z. B. `while(true);`) auf einem beliebigen Thread kann die App zum Stillstand bringen. Auf ähnliche Weise können lange oder unendliche Wartezeiten die Anwendung zum Stillstand bringen.  
  
-   Bestimmte generische Initialisierungszyklen lösen in [!INCLUDE[net_native](../../../includes/net-native-md.md)]keine Ausnahmen aus. Das folgende Codebeispiel löst eine <xref:System.TypeLoadException> -Ausnahme auf der Standard-CLR aus. In [!INCLUDE[net_native](../../../includes/net-native-md.md)]ist dies nicht der Fall.  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
-   In einigen Fällen stellt [!INCLUDE[net_native](../../../includes/net-native-md.md)] verschiedene Implementierungen von .NET Framework-Klassenbibliotheken bereit. Ein von einer Methode zurückgegebenes Objekt implementiert immer die Member des zurückgegebenen Typs. Da aber die Unterstützungsimplementierung unterschiedlich ist, können Sie es möglicherweise nicht in dieselben Typen wie auf anderen .NET Framework-Plattformen umwandeln. In einigen Fällen sind Sie zum Beispiel möglicherweise nicht in der Lage, das <xref:System.Collections.Generic.IEnumerable%601> -Schnittstellenobjekt, das von Methoden wie <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=fullName> oder <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=fullName> zurückgegeben wird, in `T[]`umzuwandeln.  
  
-   Der WinInet-Cache ist standardmäßig nicht in .NET für Windows Store-Apps aktiviert, aber in [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Dies verbessert die Leistung, hat aber Auswirkungen auf das Workingset. Es ist keine Entwickleraktion erforderlich.  
  
<a name="Dynamic"></a>   
## <a name="dynamic-programming-differences"></a>Dynamische Programmierunterschiede  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] verknüpft statisch Code aus .NET Framework, um den Code für die maximale Anwendungsleistung lokal festzulegen. Binäre Größen müssen jedoch klein bleiben, sodass nicht das gesamte .NET Framework einbezogen werden kann. Der [!INCLUDE[net_native](../../../includes/net-native-md.md)] -Compiler löst diese Beschränkung mithilfe einer Abhängigkeitsreduzierung, die Verweise auf nicht verwendeten Code entfernt. Allerdings kann es sein, dass [!INCLUDE[net_native](../../../includes/net-native-md.md)] einige Typinformationen und einigen Code nicht beibehält oder generiert, wenn diese Informationen zur Kompilierzeit nicht statisch abgeleitet werden können, sondern stattdessen dynamisch zur Laufzeit abgerufen werden.  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] ermöglicht keine Reflektion und dynamische Programmierung. Allerdings können nicht alle Typen für die Reflektion markiert werden, da die Größe des generierten Codes zu stark ansteigen würde (vor allem, da das Reflektieren von öffentlichen APIs im .NET Framework unterstützt wird). Der [!INCLUDE[net_native](../../../includes/net-native-md.md)] -Compiler trifft intelligente Entscheidungen darüber, welche Typen Reflektion unterstützen sollten, behält die Metadaten bei und generiert Code nur für diese Typen.  
  
 Beispielsweise erfordert die Datenbindung, dass eine App Eigenschaftennamen Funktionen zuordnen kann. In .NET für Windows Store-Apps verwendet die Common Language Runtime automatisch Reflektion, um diese Funktion für verwaltete Typen und öffentlich verfügbare systemeigene Typen bereitzustellen. In [!INCLUDE[net_native](../../../includes/net-native-md.md)]schließt der Compiler automatisch Metadaten für Typen ein, an die Daten gebunden werden.  
  
 Der [!INCLUDE[net_native](../../../includes/net-native-md.md)] -Compiler kann auch häufig verwendete generische Typen verarbeiten, z. B. <xref:System.Collections.Generic.List%601> und <xref:System.Collections.Generic.Dictionary%602>, die ohne Hinweise oder Richtlinien funktionieren. Das [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) -Schlüsselwort wird ebenfalls innerhalb bestimmter Grenzen unterstützt.  
  
> [!NOTE]
>  Sie sollten alle dynamischen Codepfade gründlich testen, wenn Sie Ihre Anwendung auf [!INCLUDE[net_native](../../../includes/net-native-md.md)]portieren.  
  
 Die Standardkonfiguration für [!INCLUDE[net_native](../../../includes/net-native-md.md)] ist für die meisten Entwickler ausreichend, allerdings möchten einige Entwickler ihre Konfigurationen möglicherweise mithilfe einer Laufzeitdirektivendatei (.rd.xml) optimieren. Darüber hinaus kann in einigen Fällen der [!INCLUDE[net_native](../../../includes/net-native-md.md)] Compiler nicht ermitteln, welche Metadaten für die Reflektion verfügbar sein müssen, und verlässt sich auf Hinweise, insbesondere in den folgenden Fällen:  
  
-   Einige Konstrukte wie <xref:System.Type.MakeGenericType%2A?displayProperty=fullName> und <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=fullName> können nicht statisch bestimmt werden.  
  
-   Da der Compiler die Instanziierungen nicht ermitteln kann, muss ein generischer Typ, den Sie für die Reflektion verwenden möchten, durch Laufzeitdirektiven angegeben werden. Nicht nur, weil der gesamte Code enthalten sein muss, sondern auch, weil die Reflektion für generische Typen (z. B. wenn eine generische Methode für einen generischen Typ aufgerufen wird) einen unendlichen Zyklus bilden kann.  
  
> [!NOTE]
>  Laufzeitdirektiven werden in einer Laufzeitdirektivendatei (.rd.xml) definiert. Allgemeine Informationen zur Verwendung dieser Datei finden Sie unter [Getting Started with .NET Native (Erste Schritte mit .NET Native)](../../../docs/framework/net-native/getting-started-with-net-native.md). Informationen zu Laufzeitdirektiven finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] enthält ebenfalls Profilerstellungstools, mit denen Entwickler bestimmen können, welche Typen außerhalb des Standardsatzes Reflektion unterstützen sollen.  
  
<a name="Reflection"></a>   
## <a name="other-reflection-related-differences"></a>Andere Unterschiede im Zusammenhang mit Reflektion  
 Es gibt eine Reihe von weiteren reflektionsbezogenen Unterschieden im Verhalten zwischen .NET für Windows Store-Apps und [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 In [!INCLUDE[net_native](../../../includes/net-native-md.md)]:  
  
-   Private Reflektion über Typen und Member in der .NET Framework-Klassenbibliothek wird nicht unterstützt. Sie können jedoch eigene private Typen und Member sowie Typen und Member in Bibliotheken von Drittanbietern für die Reflektion verwenden.  
  
-   Die <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=fullName> -Eigenschaft gibt ordnungsgemäß `false` für ein <xref:System.Reflection.ParameterInfo> -Objekt zurück, das einen Rückgabewert darstellt. In den .NET für Windows Store-Apps gibt es `true`zurück. Intermediate Language (IL) unterstützt dies nicht direkt, und die Interpretation bleibt der Sprache überlassen.  
  
-   Öffentliche Member in den <xref:System.RuntimeFieldHandle> - und <xref:System.RuntimeMethodHandle> -Strukturen werden nicht unterstützt. Diese Typen werden nur für LINQ, Ausdrucksbaumstrukturen und statische Arrayinitialisierungen unterstützt.  
  
-   <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=fullName> und <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=fullName> enthalten ausgeblendete Member in Basisklassen und können daher ohne explizite Überschreibungen überschrieben werden. Dies gilt auch für andere [RuntimeReflectionExtensions.GetRuntime*](http://msdn.microsoft.com/library/system.reflection.runtimereflectionextensions_methods.aspx) -Methoden.  
  
-   <xref:System.Type.MakeArrayType%2A?displayProperty=fullName> und <xref:System.Type.MakeByRefType%2A?displayProperty=fullName> schlagen nicht fehl, wenn Sie versuchen, bestimmte Kombinationen (z. B. ein Array mit ByRefs) zu erstellen.  
  
-   Sie können mithilfe der Reflektion keine Member mit Zeigerparametern aufrufen.  
  
-   Sie können mithilfe der Reflektion kein Zeigerfeld abrufen oder festlegen.  
  
-   Wenn die Anzahl der Argumente falsch ist und der Typ eines der Argumente falsch ist, löst [!INCLUDE[net_native](../../../includes/net-native-md.md)] eine <xref:System.ArgumentException> anstatt einer <xref:System.Reflection.TargetParameterCountException>aus.  
  
-   Binäre Serialisierung von Ausnahmen wird in der Regel nicht unterstützt. Daher können nicht serialisierbare Objekte zum <xref:System.Exception.Data%2A?displayProperty=fullName> -Wörterbuch hinzugefügt werden.  
  
<a name="Unsupported"></a>   
## <a name="unsupported-scenarios-and-apis"></a>Nicht unterstützte Szenarios und APIs  
 In den folgenden Abschnitten werden nicht unterstützte Szenarios und APIs für allgemeine Entwicklung, Interop und Technologien wie HTTPClient und Windows Communication Foundation (WCF) aufgelistet:  
  
-   [Allgemeine Entwicklung](#General)  
  
-   [HttpClient](#HttpClient)  
  
-   [Interop](#Interop)  
  
-   [Nicht unterstützte APIs](#APIs)  
  
<a name="General"></a>   
### <a name="general-development-differences"></a>Allgemeine Entwicklungsunterschiede  
 **Werttypen**  
  
-   Wenn Sie die <xref:System.ValueType.Equals%2A?displayProperty=fullName> - und <xref:System.ValueType.GetHashCode%2A?displayProperty=fullName> -Methoden für einen Werttyp außer Kraft setzen, rufen Sie nicht die Implementierungen der Basisklasse auf. In .NET für Windows Store-Apps sind diese Methoden auf Reflektion angewiesen. Zum Zeitpunkt der Kompilierung generiert [!INCLUDE[net_native](../../../includes/net-native-md.md)] eine Implementierung, die nicht auf die Laufzeitreflektion angewiesen ist. Dies bedeutet, dass diese beiden Methoden, wenn Sie sie nicht außer Kraft setzen, wie erwartet funktionieren, da [!INCLUDE[net_native](../../../includes/net-native-md.md)] die Implementierung zum Zeitpunkt der Kompilierung generiert. Allerdings wird durch das Außerkraftsetzen dieser Methoden und das Aufrufen der Basisklassenimplementierung eine Ausnahme ausgelöst.  
  
-   Werttypen, die größer als 1 MB sind, werden nicht unterstützt.  
  
-   Werttypen dürfen keinen Standardkonstruktor in [!INCLUDE[net_native](../../../includes/net-native-md.md)]haben. (C# und Visual Basic verbieten Standardkonstruktoren für Werttypen. Allerdings können diese in IL erstellt werden.)  
  
 **Arrays**  
  
-   Arrays mit einer unteren Grenze ungleich null werden nicht unterstützt. Diese Arrays werden in der Regel durch Aufrufen der <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=fullName> -Überladung erstellt.  
  
-   Die dynamische Erstellung von mehrdimensionalen Arrays wird nicht unterstützt. Solche Arrays werden in der Regel durch Aufruf einer Überladung für die <xref:System.Array.CreateInstance%2A?displayProperty=fullName> -Methode erstellt, die einen `lengths` -Parameter enthält, oder durch Aufrufen der <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=fullName> -Methode.  
  
-   Mehrdimensionale Arrays mit vier oder mehr Dimensionen werden nicht unterstützt. Das heißt, der <xref:System.Array.Rank%2A?displayProperty=fullName> -Eigenschaftswert ist vier oder größer. Verwenden Sie stattdessen [verzweigte Arrays](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (ein Array aus Arrays). `array[x,y,z]` ist zum Beispiel ungültig, `array[x][y][z]` aber nicht.  
  
-   Varianz für mehrdimensionale Arrays wird nicht unterstützt und verursacht eine <xref:System.InvalidCastException> -Ausnahme zur Laufzeit.  
  
 **Generika**  
  
-   Unendliche generische Typerweiterung führt zu einem Compilerfehler. Dieser Code kann z. B. nicht kompiliert werden:  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 **Zeiger**  
  
-   Arrays aus Zeigern werden nicht unterstützt.  
  
-   Sie können mithilfe der Reflektion kein Zeigerfeld abrufen oder festlegen.  
  
 **Serialisierung**  
  
 Die <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> -Attribut wird nicht unterstützt. Verwenden Sie stattdessen das <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> -Attribut.  
  
 **Ressourcen**  
  
 Die Verwendung von lokalisierten Ressourcen mit der <xref:System.Diagnostics.Tracing.EventSource> -Klasse wird nicht unterstützt. Die <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=fullName> -Eigenschaft definiert keine lokalisierten Ressourcen.  
  
 **Delegaten**  
  
 `Delegate.BeginInvoke` und `Delegate.EndInvoke` werden nicht unterstützt.  
  
 **Async**  
  
 Threadinglogik in Überladungen des IAsync-Vorgangs wird nicht unterstützt.  
  
 **Verschiedene APIs**  
  
-   Die <xref:System.Reflection.TypeInfo.GUID%2A?displayProperty=fullName> -Eigenschaft löst eine <xref:System.PlatformNotSupportedException> -Ausnahme aus, wenn ein <xref:System.Runtime.InteropServices.GuidAttribute> -Attribut nicht auf den Typ angewendet wird. Die GUID wird in erster Linie für die COM-Unterstützung verwendet.  
  
-   Die <xref:System.DateTime.Parse%2A?displayProperty=fullName> -Methode analysiert ordnungsgemäß Zeichenfolgen mit kurzen Datumsangaben im [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Sie behält allerdings keine Kompatibilität mit den Änderungen der Datums- und Uhrzeitanalyse bei, die in den Microsoft Knowledge Base-Artikeln [KB2803771](http://support.microsoft.com/kb/2803771) und [KB2803755](http://support.microsoft.com/kb/2803755)beschrieben werden.  
  
-   <xref:System.Numerics.BigInteger.ToString%2A?displayProperty=fullName> `("E")` wird in [!INCLUDE[net_native](../../../includes/net-native-md.md)]korrekt gerundet. In einigen Versionen der CLR wird die resultierende Zeichenfolge abgeschnitten und nicht gerundet.  
  
<a name="HttpClient"></a>   
### <a name="httpclient-differences"></a>HttpClient-Unterschiede  
 In [!INCLUDE[net_native](../../../includes/net-native-md.md)]verwendet die <xref:System.Net.Http.HttpClientHandler> -Klasse intern WinINet (über die [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) -Klasse) anstelle der Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> , die in den .NET für Windows Store-Standard-Apps verwendet werden.  WinINet unterstützt nicht alle Konfigurationsoptionen, die die <xref:System.Net.Http.HttpClientHandler> -Klasse unterstützt.  Ergebnis:  
  
-   Einige Funktionseigenschaften in <xref:System.Net.Http.HttpClientHandler> geben `false` für [!INCLUDE[net_native](../../../includes/net-native-md.md)]zurück, während sie `true` in den standardmäßigen .NET für Windows Store-Apps zurückgeben.  
  
-   Einige `get` -Accessoren der Konfigurationseigenschaft geben immer einen festen Wert für [!INCLUDE[net_native](../../../includes/net-native-md.md)] zurück, der sich vom konfigurierbaren Standardwert in .NET für Windows Store-Apps unterscheidet.  
  
 In den folgenden Abschnitten werden einige zusätzliche Verhaltensunterschiede behandelt.  
  
 **Proxy**  
  
 Die [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) -Klasse unterstützt nicht das Konfigurieren oder Überschreiben des Proxys auf Anforderungsbasis.  Dies bedeutet, dass alle Anforderungen für [!INCLUDE[net_native](../../../includes/net-native-md.md)] den vom System konfigurierten Proxyserver oder keinen Proxyserver verwenden, je nach Wert der <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=fullName> -Eigenschaft.  In .NET für Windows Store-Apps wird der Proxyserver durch die <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=fullName> -Eigenschaft definiert.  In [!INCLUDE[net_native](../../../includes/net-native-md.md)]wird durch das Festlegen von <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=fullName> auf einen anderen Wert als `null` eine <xref:System.PlatformNotSupportedException> -Ausnahme ausgelöst.  Die <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=fullName> -Eigenschaft gibt `false` für [!INCLUDE[net_native](../../../includes/net-native-md.md)]zurück, während sie `true` in standardmäßigen .NET Framework für Windows Store-Apps zurückgibt.  
  
 **Automatische Umleitung**  
  
 Die [HttpBaseProtocolFilter](http://msdn.microsoft.com/library/windows/apps/windows.web.http.filters.httpbaseprotocolfilter.aspx) -Klasse gestattet nicht die Konfiguration der maximalen Anzahl von automatischen Umleitungen.  Der Wert der <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=fullName> -Eigenschaft ist in den standardmäßigen .NET für Windows Store-Apps standardmäßig 50 und kann geändert werden. In [!INCLUDE[net_native](../../../includes/net-native-md.md)]ist der Wert dieser Eigenschaft 10. Beim Änderungsversuch wird eine <xref:System.PlatformNotSupportedException> -Ausnahme ausgelöst.  Die <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=fullName> -Eigenschaft gibt `false` in [!INCLUDE[net_native](../../../includes/net-native-md.md)]zurück, während sie `true` in .NET für Windows Store-Apps zurückgibt.  
  
 **Automatische Dekomprimierung**  
  
 .NET für Windows Store-Apps ermöglichen Ihnen das Festlegen der <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=fullName> -Eigenschaft auf <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, beides <xref:System.Net.DecompressionMethods.Deflate> und <xref:System.Net.DecompressionMethods.GZip>oder <xref:System.Net.DecompressionMethods.None>.  [!INCLUDE[net_native](../../../includes/net-native-md.md)] unterstützt <xref:System.Net.DecompressionMethods.Deflate> nur zusammen mit <xref:System.Net.DecompressionMethods.GZip>oder <xref:System.Net.DecompressionMethods.None>.  Wenn Sie versuchen, die <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> -Eigenschaft im Hintergrund auf <xref:System.Net.DecompressionMethods.Deflate> oder <xref:System.Net.DecompressionMethods.GZip> festzulegen, wird sie auf <xref:System.Net.DecompressionMethods.Deflate> und <xref:System.Net.DecompressionMethods.GZip>festgelegt.  
  
 **Cookies**  
  
 Cookieverarbeitung erfolgt gleichzeitig durch <xref:System.Net.Http.HttpClient> und WinINet.  Cookies aus dem <xref:System.Net.CookieContainer> werden mit Cookies im WinINet-Cookiecache kombiniert.  Durch das Entfernen eines Cookies aus <xref:System.Net.CookieContainer> wird <xref:System.Net.Http.HttpClient> am Senden des Cookies gehindert. Wenn der Cookie aber schon von WinINet erkannt wurde und Cookies nicht vom Benutzer gelöscht wurden, wird er durch WinINet gesendet.  Es ist nicht möglich, einen Cookie programmgesteuert aus WinINet mithilfe der <xref:System.Net.Http.HttpClient>-, <xref:System.Net.Http.HttpClientHandler>- oder <xref:System.Net.CookieContainer> -API zu entfernen.  Durch das Festlegen der <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=fullName> -Eigenschaft auf `false` sendet <xref:System.Net.Http.HttpClient> keine Cookies mehr; WinINet kann die Cookies immer noch in der Anforderung einschließen.  
  
 **Anmeldeinformationen**  
  
 In .NET für Windows Store-Apps funktionieren die Eigenschaften <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=fullName> und <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=fullName> unabhängig voneinander.  Darüber hinaus akzeptiert die <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft jedes Objekt, das die <xref:System.Net.ICredentials> -Schnittstelle implementiert.  In [!INCLUDE[net_native](../../../includes/net-native-md.md)]wird durch das Festlegen der <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> -Eigenschaft auf `true` die <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft zu `null`.  Außerdem kann die <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft nur auf `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>oder ein Objekt vom Typ <xref:System.Net.NetworkCredential>festgelegt werden.  Wenn ein beliebiges anderes <xref:System.Net.ICredentials> -Objekt, zum Beispiel das sehr beliebte <xref:System.Net.CredentialCache>-Objekt, der <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft zugeweisen wird, wird eine <xref:System.PlatformNotSupportedException>ausgelöst.  
  
 **Andere nicht unterstützte oder nicht konfigurierbare Features**  
  
 In [!INCLUDE[net_native](../../../includes/net-native-md.md)]:  
  
-   Der Wert der <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=fullName> -Eigenschaft ist immer <xref:System.Net.Http.ClientCertificateOption.Automatic>.  In .NET für Windows Store-Apps ist der Standardwert <xref:System.Net.Http.ClientCertificateOption.Manual>.  
  
-   Die <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=fullName> -Eigenschaft ist nicht konfigurierbar.  
  
-   Die <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=fullName> -Eigenschaft ist immer `true`.  In .NET für Windows Store-Apps ist der Standardwert `false`.  
  
-   Der `SetCookie2` -Header in Antworten wird als veraltet ignoriert.  
  
<a name="Interop"></a>   
### <a name="interop-differences"></a>Interop-Unterschiede  
 **Nicht mehr unterstützte APIs**  
  
 Eine Reihe von selten verwendeten APIs für die Interoperabilität mit verwaltetem Code werden nicht mehr unterstützt. Bei Verwendung mit [!INCLUDE[net_native](../../../includes/net-native-md.md)]können diese APIs eine <xref:System.NotImplementedException> - oder <xref:System.PlatformNotSupportedException> -Ausnahme oder einen Compilerfehler auslösen. Diese APIs sind in .NET für Windows Store-Apps als veraltet gekennzeichnet, obwohl beim Aufruf kein Compilerfehler sondern eine Compilerwarnung generiert wird.  
  
 Veraltete APIs für das `VARIANT` -Marshallen:  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.VarEnum?displayProperty=fullName>|  
  
 <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=fullName> wird unterstützt, löst aber in einigen Szenarien eine Ausnahme aus, zum Beispiel bei der Verwendung mit [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) oder ByRef-Varianten.  
  
 Veraltete APIs für [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) unterstützen Folgendes:  
  
|Typ|Member|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>|  
|<xref:System.Runtime.InteropServices.ClassInterfaceType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual>|  
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=fullName>|Attribut wird nicht unterstützt.|  
  
 Nicht mehr unterstützte APIs für klassische COM-Ereignisse:  
  
||  
|-|  
|<xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=fullName>|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|  
  
 Veraltete APIs in der <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=fullName> -Schnittstelle, die in [!INCLUDE[net_native](../../../includes/net-native-md.md)]nicht unterstützt wird:  
  
|Typ|Member|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=fullName>|Alle Member.|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=fullName>|Alle Member.|  
|<xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=fullName>|Alle Member.|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>|  
  
 Andere nicht unterstützte Interop-Features:  
  
|Typ|Member|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=fullName>|Alle Member.|  
|<xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=fullName>|Alle Member.|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.UnmanagedType.Currency>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.UnmanagedType.AsAny>|  
|<xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>|<xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler>|  
  
 Selten verwendete Marshalling-APIs:  
  
|Typ|Member|  
|----------|------------|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29>|  
|<xref:System.Runtime.InteropServices.Marshal?displayProperty=fullName>|<xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29>|  
  
 **Plattformaufruf und COM-Interop-Kompatibilität**  
  
 Die meisten Plattformaufruf- und COM-Interop-Szenarios werden in [!INCLUDE[net_native](../../../includes/net-native-md.md)]weiterhin unterstützt. Insbesondere werden die gesamte Interoperabilität mit WinRT-APIs (Windows-Runtime) und das gesamte Marshalling unterstützt, das für Windows-Runtime erforderlich ist. Dazu gehört die Marshallingunterstützung für:  
  
-   Arrays (einschließlich <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=fullName>)  
  
-   `BStr`  
  
-   Delegaten  
  
-   Zeichenfolgen (Unicode, Ansi und HSTRING)  
  
-   Strukturen (`byref` und `byval`)  
  
-   Unions  
  
-   Win32-Handles  
  
-   Alle WinRT-Konstrukte  
  
-   Teilweise Unterstützung für das Marshalling von "variant"-Typen. Folgendes wird unterstützt:  
  
    -   <xref:System.Boolean>  
  
    -   <xref:System.Byte>  
  
    -   <xref:System.Decimal>  
  
    -   <xref:System.Double>  
  
    -   <xref:System.Int16>  
  
    -   <xref:System.Int32>  
  
    -   <xref:System.Int64>  
  
    -   <xref:System.SByte>  
  
    -   <xref:System.Single>  
  
    -   <xref:System.UInt16>  
  
    -   <xref:System.UInt32>  
  
    -   <xref:System.UInt64>  
  
    -   `BStr`  
  
    -   [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509.aspx)  
  
 [!INCLUDE[net_native](../../../includes/net-native-md.md)] unterstützt jedoch nicht Folgendes:  
  
-   Verwenden von klassischen COM-Ereignissen  
  
-   Implementieren der <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=fullName> -Schnittstelle für einen verwalteten Typ  
  
-   Implementieren der [IDispatch](http://msdn.microsoft.com/library/windows/apps/ms221608.aspx) -Schnittstelle für einen verwalteten Typ über das <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=fullName> -Attribut Beachten Sie jedoch, dass Sie keine COM-Objekte durch `IDispatch`aufrufen können und das verwaltete Objekt `IDispatch`nicht implementieren kann.  
  
 Das Verwenden von Reflektion zum Aufrufen einer Plattformaufrufmethode wird nicht unterstützt. Sie können diese Einschränkung umgehen, indem Sie den Methodenaufruf in eine andere Methode einschließen und den Wrapper stattdessen mithilfe von Reflektion aufrufen.  
  
<a name="APIs"></a>   
### <a name="other-differences-from-net-apis-for-windows-store-apps"></a>Andere Unterschiede zu .NET-APIs für Windows Store-Apps  
 In diesem Abschnitt werden die verbleibenden APIs aufgelistet, die in [!INCLUDE[net_native](../../../includes/net-native-md.md)]nicht unterstützt werden. Die größte Gruppe von nicht unterstützten APIs sind APIs von Windows Communication Foundation (WCF).  
  
 **DataAnnotations (System.ComponentModel.DataAnnotations)**  
  
 Die Typen in den <xref:System.ComponentModel.DataAnnotations> - und <xref:System.ComponentModel.DataAnnotations.Schema> -Namespaces werden nicht in [!INCLUDE[net_native](../../../includes/net-native-md.md)]unterstützt. Dazu gehören die folgenden Typen, die in .NET für Windows Store-Apps für Windows 8 vorhanden sind:  
  
||  
|-|  
|<xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EditableAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>|  
|<xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=fullName>|  
|<xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=fullName>|  
  
 **Visual Basic**  
  
 Visual Basic wird derzeit nicht in [!INCLUDE[net_native](../../../includes/net-native-md.md)]unterstützt. Die folgenden Typen in den <xref:Microsoft.VisualBasic> - und <xref:Microsoft.VisualBasic.CompilerServices> - Namespaces sind in [!INCLUDE[net_native](../../../includes/net-native-md.md)]nicht verfügbar:  
  
||  
|-|  
|<xref:Microsoft.VisualBasic.CallType?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.Constants?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.Strings?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=fullName>|  
|<xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=fullName>|  
  
 **Reflection Context (System.Reflection.Context-Namespace)**  
  
 Die <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=fullName> -Klasse wird in [!INCLUDE[net_native](../../../includes/net-native-md.md)]nicht unterstützt.  
  
 **RTC (System.Net.Http.Rtc)**  
  
 Die <xref:System.Net.Http.RtcRequestFactory?displayProperty=fullName> -Klasse wird in [!INCLUDE[net_native](../../../includes/net-native-md.md)]nicht unterstützt.  
  
 **Windows Communication Foundation (WCF) (System.ServiceModel.\*)**  
  
 Die Typen in den [System.ServiceModel.*-Namespaces](http://msdn.microsoft.com/library/gg145010.aspx) werden nicht in [!INCLUDE[net_native](../../../includes/net-native-md.md)]unterstützt. Dies umfasst die folgenden Typen:  
  
||  
|-|  
|<xref:System.ServiceModel.ActionNotSupportedException?displayProperty=fullName>|  
|<xref:System.ServiceModel.BasicHttpBinding?displayProperty=fullName>|  
|<xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=fullName>|  
|<xref:System.ServiceModel.BasicHttpSecurity?displayProperty=fullName>|  
|<xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=fullName>|  
|<xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.ChannelFactory?displayProperty=fullName>|  
|<xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.ClientBase%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=fullName>|  
|<xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=fullName>|  
|<xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=fullName>|  
|<xref:System.ServiceModel.CommunicationException?displayProperty=fullName>|  
|<xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=fullName>|  
|<xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=fullName>|  
|<xref:System.ServiceModel.CommunicationState?displayProperty=fullName>|  
|<xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=fullName>|  
|<xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.DuplexClientBase%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.EndpointAddress?displayProperty=fullName>|  
|<xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=fullName>|  
|<xref:System.ServiceModel.EndpointIdentity?displayProperty=fullName>|  
|<xref:System.ServiceModel.EndpointNotFoundException?displayProperty=fullName>|  
|<xref:System.ServiceModel.EnvelopeVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.ExceptionDetail?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultCode?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultException?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultException%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultReason?displayProperty=fullName>|  
|<xref:System.ServiceModel.FaultReasonText?displayProperty=fullName>|  
|<xref:System.ServiceModel.HttpBindingBase?displayProperty=fullName>|  
|<xref:System.ServiceModel.HttpClientCredentialType?displayProperty=fullName>|  
|<xref:System.ServiceModel.HttpTransportSecurity?displayProperty=fullName>|  
|<xref:System.ServiceModel.IClientChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.ICommunicationObject?displayProperty=fullName>|  
|<xref:System.ServiceModel.IContextChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=fullName>|  
|<xref:System.ServiceModel.IExtensibleObject%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.IExtension%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.IExtensionCollection%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.InstanceContext?displayProperty=fullName>|  
|<xref:System.ServiceModel.InvalidMessageContractException?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageContractAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageCredentialType?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageHeader%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageHeaderException?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageParameterAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=fullName>|  
|<xref:System.ServiceModel.MessageSecurityVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.NetHttpBinding?displayProperty=fullName>|  
|<xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=fullName>|  
|<xref:System.ServiceModel.NetTcpBinding?displayProperty=fullName>|  
|<xref:System.ServiceModel.NetTcpSecurity?displayProperty=fullName>|  
|<xref:System.ServiceModel.OperationContext?displayProperty=fullName>|  
|<xref:System.ServiceModel.OperationContextScope?displayProperty=fullName>|  
|<xref:System.ServiceModel.OperationContractAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.OperationFormatStyle?displayProperty=fullName>|  
|<xref:System.ServiceModel.ProtocolException?displayProperty=fullName>|  
|<xref:System.ServiceModel.QuotaExceededException?displayProperty=fullName>|  
|<xref:System.ServiceModel.SecurityMode?displayProperty=fullName>|  
|<xref:System.ServiceModel.ServerTooBusyException?displayProperty=fullName>|  
|<xref:System.ServiceModel.ServiceActivationException?displayProperty=fullName>|  
|<xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=fullName>|  
|<xref:System.ServiceModel.TcpClientCredentialType?displayProperty=fullName>|  
|<xref:System.ServiceModel.TcpTransportSecurity?displayProperty=fullName>|  
|<xref:System.ServiceModel.TransferMode?displayProperty=fullName>|  
|<xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=fullName>|  
|<xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=fullName>|  
|<xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.AddressHeader?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.FaultConverter?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IInputChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IInputSession?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IOutputSession?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.ISession?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.Message?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageFault?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageHeader?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageProperties?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageState?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.MessageVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.RequestContext?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=fullName>|  
|<xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.ClientCredentials?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.ContractDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.FaultDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageDirection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.OperationDescription?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=fullName>|  
|<xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=fullName>|  
|<xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.SecurityVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.TrustVersion?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=fullName>|  
|<xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=fullName>|  
  
### <a name="differences-in-serializers"></a>Unterschiede in den Serialisierungsprogrammen  
 Die folgenden Unterschiede betreffen die Serialisierung und Deserialisierung mit den Klassen <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>und <xref:System.Xml.Serialization.XmlSerializer> :  
  
-   In [!INCLUDE[net_native](../../../includes/net-native-md.md)]können <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> eine abgeleitete Klasse, die über ein Basisklassenmember verfügt, dessen Typ kein Stammserialisierungstyp ist, nicht serialisieren oder deserialisieren. Im folgenden Code führt das Serialisieren bzw. Deserialisieren von `Y` beispielsweise zu einem Fehler:  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     Typ `InnerType` ist dem Serialisierungsprogramm nicht bekannt, da die Member der Basisklasse während der Serialisierung nicht durchlaufen werden.  
  
-   <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> können keine Klasse oder Struktur serialisieren, die die <xref:System.Collections.Generic.IEnumerable%601> -Schnittstelle implementiert. Für folgende Typen schlägt das Serialisieren oder Deserialisieren beispielsweise fehl:  
  
  
  
-   <xref:System.Xml.Serialization.XmlSerializer> kann den folgenden Objektwert nicht serialisieren, da der genaue Typ des zu serialisierenden Objekts unbekannt ist:  
  
  
  
-   <xref:System.Xml.Serialization.XmlSerializer> kann nicht serialisieren oder deserialisieren, wenn der Typ des serialisierten Objekts <xref:System.Xml.XmlQualifiedName>ist.  
  
-   Alle Serialisierungsprogramme (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>und <xref:System.Xml.Serialization.XmlSerializer>) können keinen Serialisierungscode für den Typ <xref:System.Xml.Linq.XElement?displayProperty=fullName> oder für einen Typ generieren, der <xref:System.Xml.Linq.XElement>enthält. Sie zeigen stattdessen Buildfehler an.  
  
-   Die folgenden Konstruktoren der Serialisierungstypen funktionieren möglicherweise nicht wie erwartet:  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=fullName>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29?displayProperty=fullName>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=fullName>  
  
    -   <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=fullName>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29?displayProperty=fullName>  
  
    -   <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=fullName>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29?displayProperty=fullName>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=fullName>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29?displayProperty=fullName>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29?displayProperty=fullName>  
  
    -   <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29?displayProperty=fullName>  
  
-   <xref:System.Xml.Serialization.XmlSerializer> kann keinen Code für einen Typ generieren, der über Methoden mit einem der folgenden Attribute verfügt:  
  
    -   <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    -   <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
-   <xref:System.Xml.Serialization.XmlSerializer> berücksichtigt nicht die benutzerdefinierte <xref:System.Xml.Serialization.IXmlSerializable> -Serialisierungsschnittstelle. Wenn Sie eine Klasse haben, die diese Schnittstelle implementiert, berücksichtigt <xref:System.Xml.Serialization.XmlSerializer> den Typ als veralteten CLR-Objekttyp (POCO) und serialisiert nur die öffentlichen Eigenschaften.  
  
-   Das Serialisieren eines einfachen <xref:System.Exception> -Objekts wie dem folgenden funktioniert mit <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>nicht zufriedenstellend:  
  
  
  
<a name="VS"></a>   
## <a name="visual-studio-differences"></a>Visual Studio-Unterschiede  
 **Ausnahmen und Debuggen**  
  
 Wenn Sie Anwendungen ausführen, die mit [!INCLUDE[net_native](../../../includes/net-native-md.md)] im Debugger kompiliert werden, werden Ausnahmen (erste Chance) für die folgenden Ausnahmetypen ermöglicht:  
  
-   <xref:System.MemberAccessException>  
  
-   <xref:System.TypeAccessException>  
  
 **Erstellen von Anwendungen**  
  
 Verwenden Sie die x86-Buildtools, die standardmäßig von Visual Studio verwendet werden. Sie sollten nicht die AMD64-MSBuild-Tools unter "C:\Program Files (x86)\MSBuild\12.0\bin\amd64" verwenden. Diese können Buildprobleme verursachen.  
  
 **Profiler**  
  
-   Der Visual Studio-CPU-Profiler und der XAML-Arbeitsspeicherprofiler zeigen "Nur mein Code" nicht ordnungsgemäß an.  
  
-   Der XAML-Arbeitsspeicherprofiler zeigt verwaltete Heapdaten nicht ordnungsgemäß an.  
  
-   Der CPU-Profiler identifiziert Module nicht ordnungsgemäß und zeigt Funktionsnamen mit Präfix an.  
  
 **Komponententest-Bibliotheksprojekte**  
  
 Das Aktivieren von [!INCLUDE[net_native](../../../includes/net-native-md.md)] in einer Komponententestbibliothek für ein Windows Store-Appprojekt wird nicht unterstützt und bewirkt, dass das Projekt nicht erstellt werden kann.  
  
## <a name="see-also"></a>Siehe auch  
 [Getting Started (Erste Schritte)](../../../docs/framework/net-native/getting-started-with-net-native.md)   
 [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [.NET für Windows Store-Apps – Übersicht](http://msdn.microsoft.com/library/windows/apps/br230302.aspx)   
 [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)

