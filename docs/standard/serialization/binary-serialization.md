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
ms.author: mairaw
ms.openlocfilehash: 820a43e3c766c7abc47e21ad9d8c6e9d7a1d749e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269834"
---
# <a name="binary-serialization"></a>Binäre Serialisierung

Die Serialisierung kann als Prozess der Speicherung eines Objektzustands in einem Speichermedium definiert werden. Im Rahmen dieses Vorgangs werden die öffentlichen und privaten Felder des Objekts und der Name der Klasse, einschließlich der Assembly, die die Klasse enthält, in einen Bytestream umgewandelt, der dann in einen Datenstream geschrieben wird. Wenn das Objekt anschließend deserialisiert wird, wird ein genauer Klon des ursprünglichen Objekts erstellt.

Bei der Implementierung eines Serialisierungsmechanismus in einer objektorientierten Umgebung muss vielfach zwischen einfacher Handhabung und Flexibilät abgewogen werden. Dieser Vorgang lässt sich größtenteils automatisieren, sofern Sie ausreichend Kontrolle über den Vorgang haben. Es kann beispielsweise Situationen geben, in denen eine einfache binäre Serialisierung nicht ausreichend ist, oder aus einem bestimmt Grund kann es erforderlich sein zu entscheiden, welche Felder einer Klasse serialisiert werden müssen. In den folgenden Abschnitten wird der robuste Serialisierungsmechanismus untersucht, der von .NET bereitgestellt wird, und es werden einige wichtige Funktionen hervorgehoben, mit denen Sie diesen Vorgang an Ihre Anforderungen anpassen können.

> [!NOTE]
> Der Zustand eines UTF-8- oder UTF-7-codierten Objektes wird nicht beibehalten, wenn das Objekt mit verschiedenen Versionen von .NET Framework serialisiert und deserialisiert wird.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]

Die Art der binären Serialisierung ermöglicht die Änderung der privaten Member innerhalb eines Objekts. Somit wird deren Status geändert. Andere Serialisierungsframeworks wie JSON.NET, die auf der öffentlichen API-Oberfläche ausgeführt werden, werden empfohlen.

## <a name="binary-serialization-in-net-core"></a>Binäre Serialisierung in .NET Core

.NET Core unterstützt binäre Serialisierung mit einer Teilmenge der Typen. Sie finden die Liste der unterstützten Typen im Abschnitt [Serialisierbare Typen](#serializable-types). Der definierte Satz von Typen kann zwischen .NET Framework 4.5.1 und höheren Versionen und .NET Core 2.0 und höheren Versionen serialisiert werden. Andere Implementierungen von .NET, z.B. Mono, werden nicht offiziell unterstützt, sollten jedoch ebenfalls funktionieren.

### <a name="serializable-types"></a>Serialisierbare Typen

- <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:Microsoft.CSharp.RuntimeBinder.RuntimeBinderInternalCompilerException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.AccessViolationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.AggregateException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.AppDomainUnloadedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ApplicationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ArgumentException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ArgumentNullException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ArgumentOutOfRangeException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ArithmeticException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Array?displayProperty=nameWithType>
- <xref:System.ArraySegment%601?displayProperty=nameWithType>
- <xref:System.ArrayTypeMismatchException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Attribute?displayProperty=nameWithType>
- <xref:System.BadImageFormatException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Boolean?displayProperty=nameWithType>
- <xref:System.Byte?displayProperty=nameWithType>
- <xref:System.CannotUnloadAppDomainException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Char?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList?displayProperty=nameWithType>
- <xref:System.Collections.BitArray?displayProperty=nameWithType>
- <xref:System.Collections.Comparer?displayProperty=nameWithType>
- <xref:System.Collections.DictionaryEntry?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Comparer%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.EqualityComparer%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.HashSet%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Collections.Generic.KeyValuePair%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.LinkedList%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedList%602?displayProperty=nameWithType>
- <xref:System.Collections.Generic.SortedSet%601?displayProperty=nameWithType>
- <xref:System.Collections.Generic.Stack%601?displayProperty=nameWithType>
- <xref:System.Collections.Hashtable?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.Collection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.KeyedCollection%602?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>
- <xref:System.Collections.Queue?displayProperty=nameWithType>
- <xref:System.Collections.SortedList?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.HybridDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.ListDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.StringCollection?displayProperty=nameWithType>
- <xref:System.Collections.Specialized.StringDictionary?displayProperty=nameWithType>
- <xref:System.Collections.Stack?displayProperty=nameWithType>
- `System.Collections.Generic.NonRandomizedStringEqualityComparer` (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ComponentModel.BindingList%601?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ComponentModel.Design.CheckoutException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ComponentModel.InvalidAsynchronousStateException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ComponentModel.LicenseException?displayProperty=nameWithType> (in .NET Core 2.0.4 oder höher verfügbar, wird die Serialisierung von .NET Framework zu .NET Core nicht unterstützt)
- <xref:System.ComponentModel.WarningException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ComponentModel.Win32Exception?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Configuration.ConfigurationErrorsException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Configuration.ConfigurationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Configuration.Provider.ProviderException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Configuration.SettingsPropertyIsReadOnlyException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Configuration.SettingsPropertyNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Configuration.SettingsPropertyWrongTypeException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ContextMarshalException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DBNull?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.2 oder höher)
- <xref:System.Data.Common.DbException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.ConstraintException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.DBConcurrencyException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.DataException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.DataSet?displayProperty=nameWithType>
- <xref:System.Data.DataTable?displayProperty=nameWithType> (es sei denn, Sie RemotingFormat SerializationFormat.Binary festlegen kann in diesem Fall es nur mit .NET Core 2.1 und höhere Versionen ausgetauscht werden.)
- <xref:System.Data.DeletedRowInaccessibleException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.DuplicateNameException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.EvaluateException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.InRowChangingEventException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.InvalidConstraintException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.InvalidExpressionException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.MissingPrimaryKeyException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.NoNullAllowedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.Odbc.OdbcException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.OperationAbortedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.PropertyCollection?displayProperty=nameWithType>
- <xref:System.Data.ReadOnlyException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.RowNotInTableException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.SqlClient.SqlException?displayProperty=nameWithType> (in .NET Core 2.0.4 oder höher verfügbar, wird die Serialisierung von .NET Framework zu .NET Core nicht unterstützt)
- <xref:System.Data.SqlTypes.SqlAlreadyFilledException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.SqlTypes.SqlBoolean?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlByte?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlDateTime?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlDouble?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlGuid?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt16?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt32?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlInt64?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlNotFilledException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.SqlTypes.SqlNullValueException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.SqlTypes.SqlString?displayProperty=nameWithType>
- <xref:System.Data.SqlTypes.SqlTruncateException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.SqlTypes.SqlTypeException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.StrongTypingException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.SyntaxErrorException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Data.VersionNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DataMisalignedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.DateTimeOffset?displayProperty=nameWithType>
- <xref:System.Decimal?displayProperty=nameWithType>
- `System.Diagnostics.Contracts.ContractException` (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Diagnostics.Tracing.EventSourceException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.DirectoryNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.AccountManagement.MultipleMatchesException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.AccountManagement.NoMatchingPrincipalException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.AccountManagement.PasswordException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.AccountManagement.PrincipalException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.AccountManagement.PrincipalExistsException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.AccountManagement.PrincipalOperationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.AccountManagement.PrincipalServerDownException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectExistsException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryObjectNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryOperationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.ActiveDirectory.ActiveDirectoryServerDownException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.ActiveDirectory.ForestTrustCollisionException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.ActiveDirectory.SyncFromAllServersOperationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.DirectoryServicesCOMException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.Protocols.BerConversionException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.Protocols.DirectoryException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.Protocols.DirectoryOperationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.Protocols.LdapException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DirectoryServices.Protocols.TlsOperationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DivideByZeroException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.DllNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Double?displayProperty=nameWithType>
- <xref:System.Drawing.Color?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- <xref:System.Drawing.PointF?displayProperty=nameWithType>
- <xref:System.Drawing.Rectangle?displayProperty=nameWithType>
- <xref:System.Drawing.RectangleF?displayProperty=nameWithType>
- <xref:System.Drawing.Size?displayProperty=nameWithType>
- <xref:System.Drawing.SizeF?displayProperty=nameWithType>
- <xref:System.DuplicateWaitObjectException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.EntryPointNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Enum?displayProperty=nameWithType>
- <xref:System.EventArgs?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.6 oder höher)
- <xref:System.Exception?displayProperty=nameWithType>
- <xref:System.ExecutionEngineException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.FieldAccessException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.FormatException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Globalization.CompareInfo?displayProperty=nameWithType>
- <xref:System.Globalization.CultureNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Globalization.SortVersion?displayProperty=nameWithType>
- <xref:System.Guid?displayProperty=nameWithType>
- `System.IO.Compression.ZLibException` (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.DriveNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.EndOfStreamException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.FileFormatException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.FileLoadException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.FileNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.IOException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.InternalBufferOverflowException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.InvalidDataException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.IsolatedStorage.IsolatedStorageException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IO.PathTooLongException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.IndexOutOfRangeException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.InsufficientExecutionStackException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.InsufficientMemoryException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Int16?displayProperty=nameWithType>
- <xref:System.Int32?displayProperty=nameWithType>
- <xref:System.Int64?displayProperty=nameWithType>
- <xref:System.IntPtr?displayProperty=nameWithType>
- <xref:System.InvalidCastException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.InvalidOperationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.InvalidProgramException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.InvalidTimeZoneException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.MemberAccessException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.MethodAccessException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.MissingFieldException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.MissingMemberException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.MissingMethodException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.MulticastNotSupportedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.Cookie?displayProperty=nameWithType>
- <xref:System.Net.CookieCollection?displayProperty=nameWithType>
- <xref:System.Net.CookieContainer?displayProperty=nameWithType>
- <xref:System.Net.CookieException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.HttpListenerException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.Mail.SmtpException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.Mail.SmtpFailedRecipientException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.Mail.SmtpFailedRecipientsException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.NetworkInformation.NetworkInformationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.NetworkInformation.PingException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.ProtocolViolationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.Sockets.SocketException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.WebException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Net.WebSockets.WebSocketException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.NotFiniteNumberException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.NotImplementedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.NotSupportedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.NullReferenceException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Numerics.BigInteger?displayProperty=nameWithType>
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.ObjectDisposedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.OperationCanceledException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.OutOfMemoryException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.OverflowException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.PlatformNotSupportedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.RankException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Reflection.AmbiguousMatchException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Reflection.CustomAttributeFormatException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Reflection.InvalidFilterCriteriaException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Reflection.ReflectionTypeLoadException?displayProperty=nameWithType> (in .NET Core 2.0.4 oder höher verfügbar, wird die Serialisierung von .NET Framework zu .NET Core nicht unterstützt)
- <xref:System.Reflection.TargetException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Reflection.TargetInvocationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Reflection.TargetParameterCountException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Resources.MissingManifestResourceException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Resources.MissingSatelliteAssemblyException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.CompilerServices.RuntimeWrappedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.InteropServices.COMException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.InteropServices.ExternalException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.InteropServices.InvalidComObjectException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.InteropServices.InvalidOleVariantTypeException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.InteropServices.MarshalDirectiveException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.InteropServices.SEHException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.Serialization.InvalidDataContractException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Runtime.Serialization.SerializationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.SByte?displayProperty=nameWithType>
- <xref:System.Security.AccessControl.PrivilegeNotHeldException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Security.Authentication.AuthenticationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Security.Authentication.InvalidCredentialException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Security.Cryptography.CryptographicException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Security.Cryptography.CryptographicUnexpectedOperationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- `System.Security.Cryptography.Xml.CryptoSignedXmlRecursionException` (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Security.HostProtectionException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Security.Policy.PolicyException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Security.Principal.IdentityNotMappedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Security.SecurityException?displayProperty=nameWithType> (in .NET Core 2.0.4 und höheren Versionen, begrenzte Serialisierungsdaten verfügbar)
- <xref:System.Security.VerificationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Security.XmlSyntaxException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ServiceProcess.TimeoutException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Single?displayProperty=nameWithType>
- <xref:System.StackOverflowException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.StringComparer?displayProperty=nameWithType>
- <xref:System.SystemException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Text.DecoderFallbackException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Text.EncoderFallbackException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Text.RegularExpressions.RegexMatchTimeoutException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Text.StringBuilder?displayProperty=nameWithType>
- <xref:System.Threading.AbandonedMutexException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.BarrierPostPhaseException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.LockRecursionException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.SemaphoreFullException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.SynchronizationLockException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.Tasks.TaskCanceledException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.Tasks.TaskSchedulerException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.ThreadAbortException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.ThreadInterruptedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.ThreadStartException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.ThreadStateException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Threading.WaitHandleCannotBeOpenedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.TimeSpan?displayProperty=nameWithType>
- <xref:System.TimeZoneInfo.AdjustmentRule?displayProperty=nameWithType>
- <xref:System.TimeZoneInfo?displayProperty=nameWithType>
- <xref:System.TimeZoneNotFoundException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.TimeoutException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Transactions.TransactionAbortedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Transactions.TransactionException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Transactions.TransactionInDoubtException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Transactions.TransactionManagerCommunicationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Transactions.TransactionPromotionException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Tuple?displayProperty=nameWithType>
- <xref:System.TypeAccessException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.TypeInitializationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.TypeLoadException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.TypeUnloadedException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.UInt16?displayProperty=nameWithType>
- <xref:System.UInt32?displayProperty=nameWithType>
- <xref:System.UInt64?displayProperty=nameWithType>
- <xref:System.UIntPtr?displayProperty=nameWithType>
- <xref:System.UnauthorizedAccessException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Uri?displayProperty=nameWithType>
- <xref:System.UriFormatException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.ValueTuple?displayProperty=nameWithType> (nicht serialisierbar in .NET Framework 4.7 und früheren Versionen)
- <xref:System.ValueType?displayProperty=nameWithType>
- <xref:System.Version?displayProperty=nameWithType>
- <xref:System.WeakReference%601?displayProperty=nameWithType>
- <xref:System.WeakReference?displayProperty=nameWithType>
- <xref:System.Xml.Schema.XmlSchemaException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Xml.Schema.XmlSchemaInferenceException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Xml.Schema.XmlSchemaValidationException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Xml.XPath.XPathException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Xml.XmlException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Xml.Xsl.XsltCompileException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)
- <xref:System.Xml.Xsl.XsltException?displayProperty=nameWithType> (verfügbar in .NET Core 2.0.4 oder höher)

## <a name="in-this-section"></a>In diesem Abschnitt

- [Serialisierungskonzepte](../../../docs/standard/serialization/serialization-concepts.md)\
Erläutert zwei Szenarien, in denen die Serialisierung sinnvoll eingesetzt werden kann: wenn Daten im Speicher beibehalten werden sollen und wenn Objekte über Anwendungsdomänen hinweg übergeben werden.

- [Einfache Serialisierung](../../../docs/standard/serialization/basic-serialization.md)\
Beschreibt, wie die Binärdatei und SOAP-Formatierungsprogramme verwendet werden, um Objekte zu serialisieren.

- [Selektive Serialisierung](../../../docs/standard/serialization/selective-serialization.md)\
Beschreibt, wie verhindert wird, dass einige Member einer Klasse serialisiert werden.

- [Benutzerdefinierte Serialisierung](../../../docs/standard/serialization/custom-serialization.md)\
Beschreibt, wie mithilfe der <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle die Serialisierung für eine Klasse angepasst wird.

- [Die Schritte im Serialisierungsprozess](../../../docs/standard/serialization/steps-in-the-serialization-process.md)\
Beschreibt die einzelnen Serialisierungsschritte, die ausgeführt werden, wenn die <xref:System.Runtime.Serialization.Formatter.Serialize%2A>-Methode für ein Formatierungsprogramm aufgerufen wird.

- [Versionstolerante Serialisierung](../../../docs/standard/serialization/version-tolerant-serialization.md)\
Erklärt, wie serialisierbare Typen erstellt werden, die im Lauf der Zeit modifiziert werden können, ohne dass dies zur Folge hat, dass Anwendungen Ausnahmen auslösen.

- [Serialisierungsrichtlinien](../../../docs/standard/serialization/serialization-guidelines.md)\
Stellt einige allgemeine Richtlinien zur Entscheidung der Frage bereit, wann ein Objekt serialisiert werden sollte.

## <a name="reference"></a>Referenz

- <xref:System.Runtime.Serialization>\
Enthält Klassen, mit denen Objekte serialisiert und deserialisiert werden können.

## <a name="related-sections"></a>Verwandte Abschnitte

- [XML- und SOAP-Serialisierung](../../../docs/standard/serialization/xml-and-soap-serialization.md)\
Beschreibt den XML-Serialisierungsmechanismus, der in der Common Language Runtime enthalten ist.

- [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md)\
Beschreibt Richtlinien für das Schreiben sicheren Codes, die beim Schreiben von befolgt werden sollten, der Serialisierungen durchführt.

- [Remoteobjekte](https://msdn.microsoft.com/library/515686e6-0a8d-42f7-8188-73abede57c58)\
Beschreibt die verschiedenen Kommunikationsverfahren, die in .NET&#160;Framework für die Remotekommunikation zur Verfügung stehen.

- [XML-Webdienste mit ASP.NET und XML-Webdienstclients erstellte](https://msdn.microsoft.com/library/1e64af78-d705-4384-b08d-591a45f4379c)\
Stellt Themen bereit, die beschreiben und erklären, wie mit ASP.NET erstellte XML-Webdienste programmiert werden.