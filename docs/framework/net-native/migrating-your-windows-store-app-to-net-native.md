---
title: Migrieren der Windows Store-App auf .NET Native
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e4d3d7bc574dd27aaea0d43ee6f507dd0c413f2
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063819"
---
# <a name="migrating-your-windows-store-app-to-net-native"></a>Migrieren der Windows Store-App auf .NET Native
.NET native stellt statische Kompilierung von Anwendungen in der Windows Store oder auf dem Computer des Entwicklers bereit. Dies unterscheidet sich von der dynamischen Kompilierung für Windows Store-Apps durch den JIT-Compiler (Just-in-Time) oder den [Native Image Generator (Ngen.exe)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) auf dem Gerät. Trotz der Unterschiede .NET Native versucht, Kompatibilität mit der [.NET für Windows Store-apps](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29). Zum größten Teil, der Dinge, die auf die .NET für Windows Store-apps funktionieren auch mit .NET Native.  In einigen Fällen können jedoch Verhaltensänderungen auftreten. Dieses Dokument erläutert diese Unterschiede zwischen dem standardmäßigen .NET für Windows Store-apps, und suchen Sie in der .NET Native in den folgenden Bereichen:  
  
- [Allgemeine Laufzeitunterschiede](#Runtime)  
  
- [Dynamische Programmierunterschiede](#Dynamic)  
  
- [Andere Unterschiede im Zusammenhang mit Reflektion](#Reflection)  
  
- [Nicht unterstützte Szenarios und APIs](#Unsupported)  
  
- [Visual Studio-Unterschiede](#VS)  
  
<a name="Runtime"></a>   
## <a name="general-runtime-differences"></a>Allgemeine Laufzeitunterschiede  
  
- Ausnahmen, z. B. <xref:System.TypeLoadException>, vom JIT-Compiler ausgelöst werden, beim Ausführen einer app auf der Common Language Runtime (CLR) in der Regel während der Kompilierung zu Fehlern führen, bei der Verarbeitung durch .NET Native.  
  
- Rufen Sie die <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> -Methode nicht vom UI-Thread einer Anwendung auf. Dies kann zu einem Deadlock in .NET Native führen.  
  
- Verlassen Sie sich nicht auf die Aufrufreihenfolge des statischen Klassenkonstruktors. In .NET Native unterscheidet sich die Aufrufreihenfolge von der Reihenfolge, in der Standardlaufzeit. (Auch mit der Standardlaufzeit sollten Sie sich nicht auf die Reihenfolge der Ausführung der statischen Klassenkonstruktoren verlassen.)  
  
- Endlosschleifen ohne einen Anruf (z. B. `while(true);`) auf einem beliebigen Thread kann die App zum Stillstand bringen. Auf ähnliche Weise können lange oder unendliche Wartezeiten die Anwendung zum Stillstand bringen.  
  
- Bestimmte generische initialisierungszyklen in .NET Native keine Ausnahmen auslösen. Das folgende Codebeispiel löst eine <xref:System.TypeLoadException> -Ausnahme auf der Standard-CLR aus. In .NET Native nicht wahr.  
  
     [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]  
  
- In einigen Fällen bietet .NET Native verschiedene Implementierungen von .NET Framework-Klassenbibliotheken. Ein von einer Methode zurückgegebenes Objekt implementiert immer die Member des zurückgegebenen Typs. Da aber die Unterstützungsimplementierung unterschiedlich ist, können Sie es möglicherweise nicht in dieselben Typen wie auf anderen .NET Framework-Plattformen umwandeln. In einigen Fällen sind Sie zum Beispiel möglicherweise nicht in der Lage, das <xref:System.Collections.Generic.IEnumerable%601> -Schnittstellenobjekt, das von Methoden wie <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> oder <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> zurückgegeben wird, in `T[]`umzuwandeln.  
  
- WinInet-Cache ist nicht für .NET für Windows Store-apps standardmäßig aktiviert, aber es ist in .NET Native. Dies verbessert die Leistung, hat aber Auswirkungen auf das Workingset. Es ist keine Entwickleraktion erforderlich.  
  
<a name="Dynamic"></a>   
## <a name="dynamic-programming-differences"></a>Dynamische Programmierunterschiede  
 .NET native verknüpft statisch Code aus .NET Framework, damit den Code lokal für maximale Leistung. Binäre Größen müssen jedoch klein bleiben, sodass nicht das gesamte .NET Framework einbezogen werden kann. .NET Native-Compiler löst diese Beschränkung mithilfe einer abhängigkeitsreduzierung, die Verweise auf nicht verwendeter Code entfernt. .NET Native möglicherweise nicht beibehalten oder jedoch einige Typinformationen und den Code zu generieren, wenn diese Informationen nicht zur Kompilierzeit nicht statisch abgeleitet werden, sondern stattdessen dynamisch zur Laufzeit abgerufen.  
  
 .NET native Reflektion und dynamische Programmierung zu aktivieren. Allerdings können nicht alle Typen für die Reflektion markiert werden, da die Größe des generierten Codes zu stark ansteigen würde (vor allem, da das Reflektieren von öffentlichen APIs im .NET Framework unterstützt wird). .NET Native-Compiler stellt intelligente Entscheidungen darüber, welche Typen Reflektion unterstützen sollten, und behält die Metadaten und generiert Code nur für diese Typen.  
  
 Beispielsweise erfordert die Datenbindung, dass eine App Eigenschaftennamen Funktionen zuordnen kann. In .NET für Windows Store-Apps verwendet die Common Language Runtime automatisch Reflektion, um diese Funktion für verwaltete Typen und öffentlich verfügbare systemeigene Typen bereitzustellen. In .NET Native schließt der Compiler automatisch Metadaten für Typen, die an die Daten gebunden werden.  
  
 Die .NET Native-Compiler kann auch im Allgemeinen behandeln verwendet generische Typen z. B. <xref:System.Collections.Generic.List%601> und <xref:System.Collections.Generic.Dictionary%602>, die ohne Hinweise oder Richtlinien funktionieren. Das [dynamic](~/docs/csharp/language-reference/keywords/dynamic.md) -Schlüsselwort wird ebenfalls innerhalb bestimmter Grenzen unterstützt.  
  
> [!NOTE]
>  Sie sollten alle dynamischen Codepfade gründlich testen, bei der Portierung von Ihrer app auf .NET Native.  
  
 Die Standardkonfiguration für .NET Native ist für die meisten Entwickler ausreichend, aber einige Entwickler möchten Fine ihre Konfigurationen Optimierung mithilfe einer laufzeitdirektivendatei (. rd.xml) Datei. Darüber hinaus kann in einigen Fällen die .NET Native-Compiler nicht bestimmen, welche Metadaten für die Reflektion verfügbar sein und basiert auf Hinweise, insbesondere in den folgenden Fällen:  
  
- Einige Konstrukte wie <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> und <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> können nicht statisch bestimmt werden.  
  
- Da der Compiler die Instanziierungen nicht ermitteln kann, muss ein generischer Typ, den Sie für die Reflektion verwenden möchten, durch Laufzeitdirektiven angegeben werden. Nicht nur, weil der gesamte Code enthalten sein muss, sondern auch, weil die Reflektion für generische Typen (z. B. wenn eine generische Methode für einen generischen Typ aufgerufen wird) einen unendlichen Zyklus bilden kann.  
  
> [!NOTE]
>  Laufzeitdirektiven werden in einer Laufzeitdirektivendatei (.rd.xml) definiert. Allgemeine Informationen zur Verwendung dieser Datei finden Sie unter [Getting Started with .NET Native (Erste Schritte mit .NET Native)](../../../docs/framework/net-native/getting-started-with-net-native.md). Informationen zu Laufzeitdirektiven finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
 .NET native enthält ebenfalls Profilerstellungstools, mit denen Entwickler bestimmen können, welche Typen außerhalb des Standardsatzes Reflektion unterstützen sollen.  
  
<a name="Reflection"></a>   
## <a name="other-reflection-related-differences"></a>Andere Unterschiede im Zusammenhang mit Reflektion  
 Es gibt zahlreiche andere einzelne reflektionsbezogenen Unterschieden im Verhalten zwischen den .NET für Windows Store-apps, und suchen Sie in der .NET Native.  
  
 In .NET Native:  
  
- Private Reflektion über Typen und Member in der .NET Framework-Klassenbibliothek wird nicht unterstützt. Sie können jedoch eigene private Typen und Member sowie Typen und Member in Bibliotheken von Drittanbietern für die Reflektion verwenden.  
  
- Die <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> -Eigenschaft gibt ordnungsgemäß `false` für ein <xref:System.Reflection.ParameterInfo> -Objekt zurück, das einen Rückgabewert darstellt. In den .NET für Windows Store-Apps gibt es `true`zurück. Intermediate Language (IL) unterstützt dies nicht direkt, und die Interpretation bleibt der Sprache überlassen.  
  
- Öffentliche Member in den <xref:System.RuntimeFieldHandle> - und <xref:System.RuntimeMethodHandle> -Strukturen werden nicht unterstützt. Diese Typen werden nur für LINQ, Ausdrucksbaumstrukturen und statische Arrayinitialisierungen unterstützt.  
  
- <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> und <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> enthalten ausgeblendete Member in Basisklassen und können daher ohne explizite Überschreibungen überschrieben werden. Dies gilt auch für andere [RuntimeReflectionExtensions.GetRuntime*](xref:System.Reflection.RuntimeReflectionExtensions) -Methoden.  
  
- <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> und <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> schlagen nicht fehl, wenn Sie versuchen, bestimmte Kombinationen (z. B. ein Array mit ByRefs) zu erstellen.  
  
- Sie können mithilfe der Reflektion keine Member mit Zeigerparametern aufrufen.  
  
- Sie können mithilfe der Reflektion kein Zeigerfeld abrufen oder festlegen.  
  
- Wenn die Anzahl der Argumente falsch ist, und der Typ eines der Argumente falsch ist, .NET Native löst eine <xref:System.ArgumentException> statt einer <xref:System.Reflection.TargetParameterCountException>.  
  
- Binäre Serialisierung von Ausnahmen wird in der Regel nicht unterstützt. Daher können nicht serialisierbare Objekte zum <xref:System.Exception.Data%2A?displayProperty=nameWithType> -Wörterbuch hinzugefügt werden.  
  
<a name="Unsupported"></a>   
## <a name="unsupported-scenarios-and-apis"></a>Nicht unterstützte Szenarios und APIs  
 In den folgenden Abschnitten werden nicht unterstützte Szenarios und APIs für allgemeine Entwicklung, Interop und Technologien wie HTTPClient und Windows Communication Foundation (WCF) aufgelistet:  
  
- [Allgemeine Entwicklung](#General)  
  
- [HttpClient](#HttpClient)  
  
- [Interop](#Interop)  
  
- [Nicht unterstützte APIs](#APIs)  
  
<a name="General"></a>   
### <a name="general-development-differences"></a>Allgemeine Entwicklungsunterschiede  
 **Werttypen**  
  
- Wenn Sie die <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> - und <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> -Methoden für einen Werttyp außer Kraft setzen, rufen Sie nicht die Implementierungen der Basisklasse auf. In .NET für Windows Store-Apps sind diese Methoden auf Reflektion angewiesen. Zum Zeitpunkt der Kompilierung generiert .NET Native eine Implementierung, die auf die Laufzeitreflektion angewiesen sind, nicht. Dies bedeutet, dass wenn Sie diese beiden Methoden nicht außer Kraft setzen, sie funktionieren wie erwartet, da .NET Native die Implementierung zum Zeitpunkt der Kompilierung generiert. Allerdings wird durch das Außerkraftsetzen dieser Methoden und das Aufrufen der Basisklassenimplementierung eine Ausnahme ausgelöst.  
  
- Werttypen, die größer als 1 MB sind, werden nicht unterstützt.  
  
- Einen Standardkonstruktor können nicht von Werttypen in .NET Native haben. (C# und Visual Basic verbieten Standardkonstruktoren für Werttypen. Allerdings können diese in IL erstellt werden.)  
  
 **Arrays**  
  
- Arrays mit einer unteren Grenze ungleich null werden nicht unterstützt. Diese Arrays werden in der Regel durch Aufrufen der <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> -Überladung erstellt.  
  
- Die dynamische Erstellung von mehrdimensionalen Arrays wird nicht unterstützt. Solche Arrays werden in der Regel durch Aufruf einer Überladung für die <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> -Methode erstellt, die einen `lengths` -Parameter enthält, oder durch Aufrufen der <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> -Methode.  
  
- Mehrdimensionale Arrays mit vier oder mehr Dimensionen werden nicht unterstützt. Das heißt, der <xref:System.Array.Rank%2A?displayProperty=nameWithType> -Eigenschaftswert ist vier oder größer. Verwenden Sie stattdessen [verzweigte Arrays](~/docs/csharp/programming-guide/arrays/jagged-arrays.md) (ein Array aus Arrays). `array[x,y,z]` ist zum Beispiel ungültig, `array[x][y][z]` aber nicht.  
  
- Varianz für mehrdimensionale Arrays wird nicht unterstützt und verursacht eine <xref:System.InvalidCastException> -Ausnahme zur Laufzeit.  
  
 **Generics**  
  
- Unendliche generische Typerweiterung führt zu einem Compilerfehler. Dieser Code kann z. B. nicht kompiliert werden:  
  
     [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]  
  
 **Zeiger**  
  
- Arrays aus Zeigern werden nicht unterstützt.  
  
- Sie können mithilfe der Reflektion kein Zeigerfeld abrufen oder festlegen.  
  
 **Serialisierung**  
  
 Die <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> -Attribut wird nicht unterstützt. Verwenden Sie stattdessen das <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> -Attribut.  
  
 **Ressourcen**  
  
 Die Verwendung von lokalisierten Ressourcen mit der <xref:System.Diagnostics.Tracing.EventSource> -Klasse wird nicht unterstützt. Die <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> -Eigenschaft definiert keine lokalisierten Ressourcen.  
  
 **Delegaten**  
  
 `Delegate.BeginInvoke` und `Delegate.EndInvoke` werden nicht unterstützt.  
  
 **Verschiedene APIs**  
  
- Die [TypeInfo.GUID](xref:System.Type.GUID) Eigenschaft löst eine <xref:System.PlatformNotSupportedException> Ausnahme wenn eine <xref:System.Runtime.InteropServices.GuidAttribute> Attribut ist nicht in den Typ angewendet. Die GUID wird in erster Linie für die COM-Unterstützung verwendet.  
  
- Die <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> -Methode analysiert ordnungsgemäß Zeichenfolgen mit kurzen Datumsangaben im .NET Native. Sie behält allerdings keine Kompatibilität mit den Änderungen der Datums- und Uhrzeitanalyse bei, die in den Microsoft Knowledge Base-Artikeln [KB2803771](https://support.microsoft.com/kb/2803771) und [KB2803755](https://support.microsoft.com/kb/2803755)beschrieben werden.  
  
- <xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` in .NET Native ist korrekt gerundet werden. In einigen Versionen der CLR wird die resultierende Zeichenfolge abgeschnitten und nicht gerundet.  
  
<a name="HttpClient"></a>   
### <a name="httpclient-differences"></a>HttpClient-Unterschiede  
 In .NET Native sind die <xref:System.Net.Http.HttpClientHandler> -Klasse intern WinInet (über die <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> Klasse) anstelle von der <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> Klassen, die in standardmäßigen .NET für Windows Store-apps verwendet.  WinINet unterstützt nicht alle Konfigurationsoptionen, die die <xref:System.Net.Http.HttpClientHandler> -Klasse unterstützt.  Ergebnis:  
  
- Einige Funktionseigenschaften in <xref:System.Net.Http.HttpClientHandler> zurückgeben `false` auf .NET Native, während sie zurückgeben `true` in standardmäßigen .NET für Windows Store-apps.  
  
- Einige der Konfigurationseigenschaft `get` Accessoren immer einen festen Wert zurück, auf .NET-Native, in der der konfigurierbaren Standardwert in .NET für Windows Store-apps unterscheidet.  
  
 In den folgenden Abschnitten werden einige zusätzliche Verhaltensunterschiede behandelt.  
  
 **Proxy**  
  
 Die <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> -Klasse unterstützt nicht das Konfigurieren oder Überschreiben des Proxys auf einer Basis pro Anforderung.  Dies bedeutet, dass alle Anforderungen für .NET Native das System konfigurierten Proxyserver oder keinen Proxyserver, abhängig vom Wert der <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> Eigenschaft.  In .NET für Windows Store-Apps wird der Proxyserver durch die <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> -Eigenschaft definiert.  In .NET Native, Festlegen der <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> auf einen anderen Wert als `null` löst eine <xref:System.PlatformNotSupportedException> Ausnahme.  Die <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> -Eigenschaft gibt `false` auf .NET Native, während wird `true` in standardmäßigen .NET Framework für Windows Store-apps.  
  
 **Automatische Umleitung**  
  
 Die <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> -Klasse gestattet nicht die maximale Anzahl von automatischen umleitungen konfiguriert werden.  Der Wert der <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> -Eigenschaft ist in den standardmäßigen .NET für Windows Store-Apps standardmäßig 50 und kann geändert werden. Der Wert dieser Eigenschaft auf .NET Native ist, 10 und beim Änderungsversuch eine <xref:System.PlatformNotSupportedException> Ausnahme.  Die <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> -Eigenschaft gibt `false` auf .NET Native, während wird `true` in .NET für Windows Store-apps.  
  
 **Automatische Dekomprimierung**  
  
 .NET für Windows Store-Apps ermöglichen Ihnen das Festlegen der <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> -Eigenschaft auf <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, beides <xref:System.Net.DecompressionMethods.Deflate> und <xref:System.Net.DecompressionMethods.GZip>oder <xref:System.Net.DecompressionMethods.None>.  .NET native unterstützt nur <xref:System.Net.DecompressionMethods.Deflate> zusammen mit <xref:System.Net.DecompressionMethods.GZip>, oder <xref:System.Net.DecompressionMethods.None>.  Wenn Sie versuchen, die <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> -Eigenschaft im Hintergrund auf <xref:System.Net.DecompressionMethods.Deflate> oder <xref:System.Net.DecompressionMethods.GZip> festzulegen, wird sie auf <xref:System.Net.DecompressionMethods.Deflate> und <xref:System.Net.DecompressionMethods.GZip>festgelegt.  
  
 **Cookies**  
  
 Cookieverarbeitung erfolgt gleichzeitig durch <xref:System.Net.Http.HttpClient> und WinINet.  Cookies aus dem <xref:System.Net.CookieContainer> werden mit Cookies im WinINet-Cookiecache kombiniert.  Durch das Entfernen eines Cookies aus <xref:System.Net.CookieContainer> wird <xref:System.Net.Http.HttpClient> am Senden des Cookies gehindert. Wenn der Cookie aber schon von WinINet erkannt wurde und Cookies nicht vom Benutzer gelöscht wurden, wird er durch WinINet gesendet.  Es ist nicht möglich, einen Cookie programmgesteuert aus WinINet mithilfe der <xref:System.Net.Http.HttpClient>-, <xref:System.Net.Http.HttpClientHandler>- oder <xref:System.Net.CookieContainer> -API zu entfernen.  Durch das Festlegen der <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> -Eigenschaft auf `false` sendet <xref:System.Net.Http.HttpClient> keine Cookies mehr; WinINet kann die Cookies immer noch in der Anforderung einschließen.  
  
 **Anmeldeinformationen**  
  
 In .NET für Windows Store-Apps funktionieren die Eigenschaften <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> und <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> unabhängig voneinander.  Darüber hinaus akzeptiert die <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft jedes Objekt, das die <xref:System.Net.ICredentials> -Schnittstelle implementiert.  In .NET Native, Festlegen der <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> Eigenschaft `true` bewirkt, dass die <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft zu `null`.  Außerdem kann die <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft nur auf `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>oder ein Objekt vom Typ <xref:System.Net.NetworkCredential>festgelegt werden.  Wenn ein beliebiges anderes <xref:System.Net.ICredentials> -Objekt, zum Beispiel das sehr beliebte <xref:System.Net.CredentialCache>-Objekt, der <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft zugeweisen wird, wird eine <xref:System.PlatformNotSupportedException>ausgelöst.  
  
 **Andere nicht unterstützte oder nicht konfigurierbare Features**  
  
 In .NET Native:  
  
- Der Wert der <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> -Eigenschaft ist immer <xref:System.Net.Http.ClientCertificateOption.Automatic>.  In .NET für Windows Store-Apps ist der Standardwert <xref:System.Net.Http.ClientCertificateOption.Manual>.  
  
- Die <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> -Eigenschaft ist nicht konfigurierbar.  
  
- Die <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> -Eigenschaft ist immer `true`.  In .NET für Windows Store-Apps ist der Standardwert `false`.  
  
- Der `SetCookie2` -Header in Antworten wird als veraltet ignoriert.  
  
<a name="Interop"></a>   
### <a name="interop-differences"></a>Interop-Unterschiede  
 **Nicht mehr unterstützte APIs**  
  
 Eine Reihe von selten verwendeten APIs für die Interoperabilität mit verwaltetem Code werden nicht mehr unterstützt. Bei Verwendung mit .NET Native diese APIs lösen möglicherweise eine <xref:System.NotImplementedException> oder <xref:System.PlatformNotSupportedException> -Ausnahme oder einen Compilerfehler. Diese APIs sind in .NET für Windows Store-Apps als veraltet gekennzeichnet, obwohl beim Aufruf kein Compilerfehler sondern eine Compilerwarnung generiert wird.  
  
 Veraltete APIs für `VARIANT` Marshalling enthalten:  

- <xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>  
- <xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>  
- <xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>
  
 <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> wird unterstützt, löst aber in einigen Szenarien eine Ausnahme aus, zum Beispiel bei der Verwendung mit [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) oder ByRef-Varianten.  
  
 Veraltete APIs für [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) unterstützen:  
  
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual?displayProperty=fullName> 
- <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>  

Veraltete APIs für klassische COM-Ereignisse sind:

- <xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>
  
Veraltete APIs in der <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> -Schnittstelle, die in .NET Native nicht unterstützt wird, gehören:  
  
- <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (alle Elemente)  
- <xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (alle Elemente)  
- <xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (alle Elemente)  
- <xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>  
  
Andere nicht unterstützten Interop-Funktionen gehören:  
  
- <xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (alle Elemente)  
- <xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (alle Elemente)  
- <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.UnmanagedType.AsAny?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler?displayProperty=fullName>  
  
 Selten verwendete Marshalling-APIs:  
  
- <xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29?displayProperty=fullName>  
- <xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29?displayProperty=fullName>  
  
 **Plattformaufruf und COM-Interop-Kompatibilität**  
  
 Die meisten Plattformaufruf- und COM-Interop-Szenarien werden weiterhin in .NET Native unterstützt. Insbesondere werden die gesamte Interoperabilität mit WinRT-APIs (Windows-Runtime) und das gesamte Marshalling unterstützt, das für Windows-Runtime erforderlich ist. Dazu gehört die Marshallingunterstützung für:  
  
- Arrays (einschließlich <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)  
  
- `BStr`  
  
- Delegaten  
  
- Zeichenfolgen (Unicode, Ansi und HSTRING)  
  
- Strukturen (`byref` und `byval`)  
  
- Unions  
  
- Win32-Handles  
  
- Alle WinRT-Konstrukte  
  
- Teilweise Unterstützung für das Marshalling von "variant"-Typen. Folgendes wird unterstützt:  
  
    - <xref:System.Boolean>  
  
    - <xref:System.Byte>  
  
    - <xref:System.Decimal>  
  
    - <xref:System.Double>  
  
    - <xref:System.Int16>  
  
    - <xref:System.Int32>  
  
    - <xref:System.Int64>  
  
    - <xref:System.SByte>  
  
    - <xref:System.Single>  
  
    - <xref:System.UInt16>  
  
    - <xref:System.UInt32>  
  
    - <xref:System.UInt64>  
  
    - `BStr`  
  
    - [IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown)  
  
 Unterstützt jedoch keine .NET Native Folgendes:  
  
- Verwenden von klassischen COM-Ereignissen  
  
- Implementieren der <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> -Schnittstelle für einen verwalteten Typ  
  
- Implementieren der [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) -Schnittstelle für einen verwalteten Typ über das <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> -Attribut Beachten Sie jedoch, dass Sie keine COM-Objekte durch `IDispatch`aufrufen können und das verwaltete Objekt `IDispatch`nicht implementieren kann.  
  
 Das Verwenden von Reflektion zum Aufrufen einer Plattformaufrufmethode wird nicht unterstützt. Sie können diese Einschränkung umgehen, indem Sie den Methodenaufruf in eine andere Methode einschließen und den Wrapper stattdessen mithilfe von Reflektion aufrufen.  
  
<a name="APIs"></a>   
### <a name="other-differences-from-net-apis-for-windows-store-apps"></a>Andere Unterschiede zu .NET-APIs für Windows Store-Apps  
 Dieser Abschnitt enthält die verbleibenden APIs, die in .NET Native nicht unterstützt werden. Die größte Gruppe von nicht unterstützten APIs sind APIs von Windows Communication Foundation (WCF).  
  
 **DataAnnotations (System.ComponentModel.DataAnnotations)**  
  
 Die Typen in der <xref:System.ComponentModel.DataAnnotations> und <xref:System.ComponentModel.DataAnnotations.Schema> Namespaces werden in .NET Native nicht unterstützt. Dazu gehören die folgenden Typen, die in .NET für Windows Store-apps für Windows 8 vorhanden sind:  
  
- <xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>
- <xref:System.ComponentModel.DataAnnotations.EditableAttribute>  
- <xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>  
- <xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>  
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>  
  
 **Visual Basic**  
  
 Visual Basic wird derzeit in .NET Native nicht unterstützt. Die folgenden Typen in der <xref:Microsoft.VisualBasic> und <xref:Microsoft.VisualBasic.CompilerServices> Namespaces nicht in .NET Native verfügbar sind:  

- <xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>  
- <xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>  
  
 **Reflection Context (System.Reflection.Context-Namespace)**  
  
 Die <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> Klasse wird im .NET Native nicht unterstützt.  
  
 **RTC (System.Net.Http.Rtc)**  
  
 Die `System.Net.Http.RtcRequestFactory` Klasse wird im .NET Native nicht unterstützt.  
  
 **Windows Communication Foundation (WCF) (System.ServiceModel.\*)**  
  
 Die Typen in der [System.ServiceModel-Namespaces](xref:System.ServiceModel) in .NET Native nicht unterstützt. Dies umfasst die folgenden Typen:  
  
- <xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>  
- <xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>  
- <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>  
- <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>  
- <xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>  
- <xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>  
- <xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>  
- <xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>  
- <xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>  
- <xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>  
- <xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>  
- <xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>  
- <xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>  
- <xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>  
- <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>  
- <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>  
- <xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>  
- <xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>  
- <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>  
- <xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>  
  
### <a name="differences-in-serializers"></a>Unterschiede in den Serialisierungsprogrammen  
 Die folgenden Unterschiede betreffen die Serialisierung und Deserialisierung mit den Klassen <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>und <xref:System.Xml.Serialization.XmlSerializer> :  
  
- In .NET Native sind <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> zum Serialisieren oder Deserialisieren einer abgeleiteten Klasse, die über ein Basisklassenmember verfügt, dessen Typ ist ein Stammtyp für Serialisierung nicht, fehlschlagen. Im folgenden Code führt das Serialisieren bzw. Deserialisieren von `Y` beispielsweise zu einem Fehler:  
  
     [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]  
  
     Typ `InnerType` ist dem Serialisierungsprogramm nicht bekannt, da die Member der Basisklasse während der Serialisierung nicht durchlaufen werden.  
  
- <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> können keine Klasse oder Struktur serialisieren, die die <xref:System.Collections.Generic.IEnumerable%601> -Schnittstelle implementiert. Für folgende Typen schlägt das Serialisieren oder Deserialisieren beispielsweise fehl:  

- <xref:System.Xml.Serialization.XmlSerializer> kann den folgenden Objektwert nicht serialisieren, da der genaue Typ des zu serialisierenden Objekts unbekannt ist:  

- <xref:System.Xml.Serialization.XmlSerializer> kann nicht serialisieren oder deserialisieren, wenn der Typ des serialisierten Objekts <xref:System.Xml.XmlQualifiedName>ist.  
  
- Alle Serialisierungsprogramme (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>und <xref:System.Xml.Serialization.XmlSerializer>) können keinen Serialisierungscode für den Typ <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> oder für einen Typ generieren, der <xref:System.Xml.Linq.XElement>enthält. Sie zeigen stattdessen Buildfehler an.  
  
- Die folgenden Konstruktoren der Serialisierungstypen funktionieren möglicherweise nicht wie erwartet:  
  
    - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29?displayProperty=nameWithType>  
  
    - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29?displayProperty=nameWithType>  
  
    - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29?displayProperty=nameWithType>  
  
    - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29?displayProperty=nameWithType>  
  
    - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType>  
  
    - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29?displayProperty=nameWithType>  
  
    - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29?displayProperty=nameWithType>  
  
    - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29?displayProperty=nameWithType>  
  
- <xref:System.Xml.Serialization.XmlSerializer> kann keinen Code für einen Typ generieren, der über Methoden mit einem der folgenden Attribute verfügt:  
  
    - <xref:System.Runtime.Serialization.OnSerializingAttribute>  
  
    - <xref:System.Runtime.Serialization.OnSerializedAttribute>  
  
    - <xref:System.Runtime.Serialization.OnDeserializingAttribute>  
  
    - <xref:System.Runtime.Serialization.OnDeserializedAttribute>  
  
- <xref:System.Xml.Serialization.XmlSerializer> berücksichtigt nicht die benutzerdefinierte <xref:System.Xml.Serialization.IXmlSerializable> -Serialisierungsschnittstelle. Wenn Sie eine Klasse haben, die diese Schnittstelle implementiert, berücksichtigt <xref:System.Xml.Serialization.XmlSerializer> den Typ als veralteten CLR-Objekttyp (POCO) und serialisiert nur die öffentlichen Eigenschaften.  
  
- Serialisieren eines einfachen <xref:System.Exception> Objekt funktioniert nicht gut mit <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.

<a name="VS"></a>   
## <a name="visual-studio-differences"></a>Visual Studio-Unterschiede  
 **Ausnahmen und Debuggen**  
  
 Wenn Sie apps, die Kompilierung mit .NET Native im Debugger ausführen, werden Ausnahmen für die folgenden Ausnahmetypen aktiviert:  
  
- <xref:System.MemberAccessException>  
  
- <xref:System.TypeAccessException>  
  
 **Erstellen von Anwendungen**  
  
 Verwenden Sie die x86-Buildtools, die standardmäßig von Visual Studio verwendet werden. Sie sollten nicht die AMD64-MSBuild-Tools unter "C:\Program Files (x86)\MSBuild\12.0\bin\amd64" verwenden. Diese können Buildprobleme verursachen.  
  
 **Profiler**  
  
- Der Visual Studio-CPU-Profiler und der XAML-Arbeitsspeicherprofiler zeigen "Nur mein Code" nicht ordnungsgemäß an.  
  
- Der XAML-Arbeitsspeicherprofiler zeigt verwaltete Heapdaten nicht ordnungsgemäß an.  
  
- Der CPU-Profiler identifiziert Module nicht ordnungsgemäß und zeigt Funktionsnamen mit Präfix an.  
  
 **Komponententest-Bibliotheksprojekte**  
  
 Aktivieren von .NET Native auf einer Komponententestbibliothek für ein Windows Store-App-Projekt wird nicht unterstützt und bewirkt, dass das Projekt nicht erstellt werden.  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte](../../../docs/framework/net-native/getting-started-with-net-native.md)
- [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [.NET für Windows Store-apps – Übersicht](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29)
- [.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
