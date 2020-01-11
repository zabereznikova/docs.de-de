---
title: Binäre Serialisierung
ms.date: 01/02/2018
helpviewer_keywords:
- binary serialization
- serialization, about serialization
- deserialization
- binary serialization, about serialization
- binary serialization, .net core serialization
- serialization, cross-framework
ms.assetid: 2b1ea3be-1152-4032-b2b3-07794054c405
author: ViktorHofer
ms.openlocfilehash: 9df9b73a1a1347b952d76b76c9058578f5e9f401
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901052"
---
# <a name="binary-serialization"></a>Binäre Serialisierung

Die Serialisierung kann als Prozess der Speicherung eines Objektzustands in einem Speichermedium definiert werden. Im Rahmen dieses Vorgangs werden die öffentlichen und privaten Felder des Objekts und der Name der Klasse, einschließlich der Assembly, die die Klasse enthält, in einen Bytestream umgewandelt, der dann in einen Datenstream geschrieben wird. Wenn das Objekt anschließend deserialisiert wird, wird ein genauer Klon des ursprünglichen Objekts erstellt.

Bei der Implementierung eines Serialisierungsmechanismus in einer objektorientierten Umgebung muss vielfach zwischen einfacher Handhabung und Flexibilät abgewogen werden. Dieser Vorgang lässt sich größtenteils automatisieren, sofern Sie ausreichend Kontrolle über den Vorgang haben. Es kann beispielsweise Situationen geben, in denen eine einfache binäre Serialisierung nicht ausreichend ist, oder aus einem bestimmt Grund kann es erforderlich sein zu entscheiden, welche Felder einer Klasse serialisiert werden müssen. In den folgenden Abschnitten wird der robuste Serialisierungsmechanismus untersucht, der von .NET bereitgestellt wird, und es werden einige wichtige Funktionen hervorgehoben, mit denen Sie diesen Vorgang an Ihre Anforderungen anpassen können.

> [!NOTE]
> Der Zustand eines UTF-8- oder UTF-7-codierten Objektes wird nicht beibehalten, wenn das Objekt mit verschiedenen Versionen von .NET Framework serialisiert und deserialisiert wird.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Die binäre Serialisierung ermöglicht das ändern privater Member innerhalb eines Objekts und somit die Änderung des Zustands. Aus diesem Grund werden andere serialisierungsframe Works wie <xref:System.Text.Json?displayProperty=fullName>empfohlen, die auf der öffentlichen API-Oberfläche funktionieren.

## <a name="net-core"></a>.NET Core

.Net Core unterstützt die binäre Serialisierung für eine Teilmenge von Typen. Die Liste der unterstützten Typen finden Sie im nachfolgenden Abschnitt zu [serialisierbaren Typen](#serializable-types) . Die aufgelisteten Typen sind garantiert serialisierbar zwischen .NET Framework 4.5.1 und höheren Versionen und zwischen .net Core 2,0 und höheren Versionen. Andere .net-Implementierungen, wie z. b. Mono, werden nicht offiziell unterstützt, sollten aber auch funktionieren.

### <a name="serializable-types"></a>Serialisierbare Typen

> [!div class="mx-tdCol2BreakAll"]
> | Typ | Hinweise |
> | - | - |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.AccessViolationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.AggregateException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ApplicationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ArgumentException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ArgumentNullException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ArithmeticException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Array?displayProperty=nameWithType> | |
> | <xref:System.ArraySegment%601?displayProperty=nameWithType> | |
> | <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Attribute?displayProperty=nameWithType> | |
> | <xref:System.BadImageFormatException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Boolean?displayProperty=nameWithType> | |
> | <xref:System.Byte?displayProperty=nameWithType> | |
> | <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Char?displayProperty=nameWithType> | |
> | <xref:System.Collections.ArrayList?displayProperty=nameWithType> | |
> | <xref:System.Collections.BitArray?displayProperty=nameWithType> | |
> | <xref:System.Collections.Comparer?displayProperty=nameWithType> | |
> | <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Hashtable?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType> | |
> | <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> | |
> | <xref:System.Collections.Queue?displayProperty=nameWithType> | |
> | <xref:System.Collections.SortedList?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType> | |
> | <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType> | |
> | <xref:System.Collections.Stack?displayProperty=nameWithType> | |
> | `System.Collections.Generic.NonRandomizedStringEqualityComparer` | Ab .net Core 2.0.4. |
> | <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType> | |
> | <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> | Ab .net Core 2.0.4.<br/>Die Serialisierung von .NET Framework zu .net Core wird nicht unterstützt. |
> | <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ContextMarshalException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DBNull?displayProperty=nameWithType> | Ab .net Core 2.0.2 und höheren Versionen. |
> | <xref:System.Data.Common.DbException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.ConstraintException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.DataException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.DataSet?displayProperty=nameWithType> | |
> | <xref:System.Data.DataTable?displayProperty=nameWithType> | Wenn Sie `RemotingFormat` auf `SerializationFormat.Binary`festlegen, kann es nur mit .net Core 2,1 und höheren Versionen ausgetauscht werden. |
> | <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.EvaluateException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.PropertyCollection?displayProperty=nameWithType> | |
> | <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> | Ab .net Core 2.0.4.<br/>Die Serialisierung von .NET Framework zu .net Core wird nicht unterstützt. |
> | <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType> | |
> | <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.StrongTypingException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DataMisalignedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DateTime?displayProperty=nameWithType> | |
> | <xref:System.DateTimeOffset?displayProperty=nameWithType> | |
> | <xref:System.Decimal?displayProperty=nameWithType> | |
> | `System.Diagnostics.Contracts.ContractException` | Ab .net Core 2.0.4. |
> | <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DivideByZeroException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.DllNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Double?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Color?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Point?displayProperty=nameWithType> | |
> | <xref:System.Drawing.PointF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Rectangle?displayProperty=nameWithType> | |
> | <xref:System.Drawing.RectangleF?displayProperty=nameWithType> | |
> | <xref:System.Drawing.Size?displayProperty=nameWithType> | |
> | <xref:System.Drawing.SizeF?displayProperty=nameWithType> | |
> | <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Enum?displayProperty=nameWithType> | |
> | <xref:System.EventArgs?displayProperty=nameWithType> | Ab .net Core 2.0.6. |
> | <xref:System.Exception?displayProperty=nameWithType> | |
> | <xref:System.ExecutionEngineException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.FieldAccessException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.FormatException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> | |
> | <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Globalization.SortVersion?displayProperty=nameWithType> | |
> | <xref:System.Guid?displayProperty=nameWithType> | |
> | `System.IO.Compression.ZLibException` | Ab .net Core 2.0.4. |
> | <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IO.FileFormatException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IO.FileLoadException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IO.IOException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IO.InvalidDataException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IO.PathTooLongException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.InsufficientMemoryException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Int16?displayProperty=nameWithType> | |
> | <xref:System.Int32?displayProperty=nameWithType> | |
> | <xref:System.Int64?displayProperty=nameWithType> | |
> | <xref:System.IntPtr?displayProperty=nameWithType> | |
> | <xref:System.InvalidCastException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.InvalidOperationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.InvalidProgramException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.MemberAccessException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.MethodAccessException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.MissingFieldException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.MissingMemberException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.MissingMethodException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.Cookie?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieCollection?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieContainer?displayProperty=nameWithType> | |
> | <xref:System.Net.CookieException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.HttpListenerException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.WebException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.NotFiniteNumberException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.NotImplementedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.NotSupportedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.NullReferenceException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Nullable%601?displayProperty=nameWithType> | |
> | <xref:System.Numerics.BigInteger?displayProperty=nameWithType> | |
> | <xref:System.Numerics.Complex?displayProperty=nameWithType> | |
> | <xref:System.Object?displayProperty=nameWithType> | |
> | <xref:System.ObjectDisposedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.OperationCanceledException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.OutOfMemoryException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.OverflowException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.RankException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> | Ab .net Core 2.0.4.<br/>Die Serialisierung von .NET Framework zu .net Core wird nicht unterstützt. |
> | <xref:System.Reflection.TargetException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.SByte?displayProperty=nameWithType> | |
> | <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` | Ab .net Core 2.0.4. |
> | <xref:System.Security.HostProtectionException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Security.SecurityException?displayProperty=nameWithType> | Ab .net Core 2.0.4.<br/>Eingeschränkte Serialisierungsdaten. |
> | <xref:System.Security.VerificationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Single?displayProperty=nameWithType> | |
> | <xref:System.StackOverflowException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.String?displayProperty=nameWithType> | |
> | <xref:System.StringComparer?displayProperty=nameWithType> | |
> | <xref:System.SystemException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Text.StringBuilder?displayProperty=nameWithType> | |
> | <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.TimeSpan?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneInfo?displayProperty=nameWithType> | |
> | <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.TimeoutException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Transactions.TransactionException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Tuple?displayProperty=nameWithType> | |
> | <xref:System.TypeAccessException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.TypeInitializationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.TypeLoadException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.TypeUnloadedException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.UInt16?displayProperty=nameWithType> | |
> | <xref:System.UInt32?displayProperty=nameWithType> | |
> | <xref:System.UInt64?displayProperty=nameWithType> | |
> | <xref:System.UIntPtr?displayProperty=nameWithType> | |
> | <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Uri?displayProperty=nameWithType> | |
> | <xref:System.UriFormatException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.ValueTuple?displayProperty=nameWithType> | Nicht serialisierbar in .NET Framework 4,7 und früheren Versionen. |
> | <xref:System.ValueType?displayProperty=nameWithType> | |
> | <xref:System.Version?displayProperty=nameWithType> | |
> | <xref:System.WeakReference%601?displayProperty=nameWithType> | |
> | <xref:System.WeakReference?displayProperty=nameWithType> | |
> | <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Xml.XmlException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |
> | <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> | Ab .net Core 2.0.4. |

## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.Serialization>\
Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.

- [XML and SOAP Serialization (XML- und SOAP-Serialisierung)](../../../docs/standard/serialization/xml-and-soap-serialization.md)\
Beschreibt den XML-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.

- [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md)\
Beschreibt Richtlinien für das Schreiben sicheren Codes, die beim Schreiben von befolgt werden sollten, der Serialisierungen durchführt.

- [.NET-Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)) -\
Beschreibt die verschiedenen Methoden, die in .NET Framework für die Remote Kommunikation beginnen.

- [Mit ASP.net-und XML-Webdienst Clients erstellte XML-Webdienste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7bkzywba(v=vs.100))\
Artikel, die beschreiben und erläutern, wie Sie mit ASP.NET erstellte XML-Webdienste programmieren.
