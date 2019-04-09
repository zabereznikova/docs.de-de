---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164683"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="1a8a8-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="1a8a8-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="1a8a8-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="1a8a8-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="1a8a8-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="1a8a8-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="1a8a8-105">Der Microsoft SQL Server OLE DB-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="1a8a8-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="1a8a8-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="1a8a8-106">Tables</span></span>  
  
-   <span data-ttu-id="1a8a8-107">Spalten</span><span class="sxs-lookup"><span data-stu-id="1a8a8-107">Columns</span></span>  
  
-   <span data-ttu-id="1a8a8-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1a8a8-108">Procedures</span></span>  
  
-   <span data-ttu-id="1a8a8-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1a8a8-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="1a8a8-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="1a8a8-110">Catalog</span></span>  
  
-   <span data-ttu-id="1a8a8-111">Indizes</span><span class="sxs-lookup"><span data-stu-id="1a8a8-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1a8a8-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="1a8a8-112">Tables</span></span>  
  
|<span data-ttu-id="1a8a8-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-113">ColumnName</span></span>|<span data-ttu-id="1a8a8-114">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-115">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-116">String</span></span>|  
|<span data-ttu-id="1a8a8-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-118">String</span></span>|  
|<span data-ttu-id="1a8a8-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-119">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-120">String</span></span>|  
|<span data-ttu-id="1a8a8-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-121">TABLE_TYPE</span></span>|<span data-ttu-id="1a8a8-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-122">String</span></span>|  
|<span data-ttu-id="1a8a8-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-123">TABLE_GUID</span></span>|<span data-ttu-id="1a8a8-124">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-124">Guid</span></span>|  
|<span data-ttu-id="1a8a8-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-125">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-126">String</span></span>|  
|<span data-ttu-id="1a8a8-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-127">TABLE_PROPID</span></span>|<span data-ttu-id="1a8a8-128">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-128">Int64</span></span>|  
|<span data-ttu-id="1a8a8-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-129">DATE_CREATED</span></span>|<span data-ttu-id="1a8a8-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-130">DateTime</span></span>|  
|<span data-ttu-id="1a8a8-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-131">DATE_MODIFIED</span></span>|<span data-ttu-id="1a8a8-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1a8a8-133">Spalten</span><span class="sxs-lookup"><span data-stu-id="1a8a8-133">Columns</span></span>  
  
|<span data-ttu-id="1a8a8-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-134">ColumnName</span></span>|<span data-ttu-id="1a8a8-135">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-136">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-137">String</span></span>|  
|<span data-ttu-id="1a8a8-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-139">String</span></span>|  
|<span data-ttu-id="1a8a8-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-140">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-141">String</span></span>|  
|<span data-ttu-id="1a8a8-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-142">COLUMN_NAME</span></span>|<span data-ttu-id="1a8a8-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-143">String</span></span>|  
|<span data-ttu-id="1a8a8-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-144">COLUMN_GUID</span></span>|<span data-ttu-id="1a8a8-145">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-145">Guid</span></span>|  
|<span data-ttu-id="1a8a8-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-146">COLUMN_PROPID</span></span>|<span data-ttu-id="1a8a8-147">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-147">Int64</span></span>|  
|<span data-ttu-id="1a8a8-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="1a8a8-149">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-149">Int64</span></span>|  
|<span data-ttu-id="1a8a8-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1a8a8-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1a8a8-151">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-151">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1a8a8-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1a8a8-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-153">String</span></span>|  
|<span data-ttu-id="1a8a8-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1a8a8-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="1a8a8-155">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-155">Int64</span></span>|  
|<span data-ttu-id="1a8a8-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-156">IS_NULLABLE</span></span>|<span data-ttu-id="1a8a8-157">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-157">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-158">DATA_TYPE</span></span>|<span data-ttu-id="1a8a8-159">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-159">Int32</span></span>|  
|<span data-ttu-id="1a8a8-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-160">TYPE_GUID</span></span>|<span data-ttu-id="1a8a8-161">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-161">Guid</span></span>|  
|<span data-ttu-id="1a8a8-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1a8a8-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1a8a8-163">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-163">Int64</span></span>|  
|<span data-ttu-id="1a8a8-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1a8a8-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1a8a8-165">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-165">Int64</span></span>|  
|<span data-ttu-id="1a8a8-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1a8a8-167">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-167">Int32</span></span>|  
|<span data-ttu-id="1a8a8-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="1a8a8-169">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-169">Int16</span></span>|  
|<span data-ttu-id="1a8a8-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="1a8a8-171">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-171">Int64</span></span>|  
|<span data-ttu-id="1a8a8-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1a8a8-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-173">String</span></span>|  
|<span data-ttu-id="1a8a8-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1a8a8-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-175">String</span></span>|  
|<span data-ttu-id="1a8a8-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1a8a8-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-177">String</span></span>|  
|<span data-ttu-id="1a8a8-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="1a8a8-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-179">String</span></span>|  
|<span data-ttu-id="1a8a8-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1a8a8-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-181">String</span></span>|  
|<span data-ttu-id="1a8a8-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-182">COLLATION_NAME</span></span>|<span data-ttu-id="1a8a8-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-183">String</span></span>|  
|<span data-ttu-id="1a8a8-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1a8a8-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-185">String</span></span>|  
|<span data-ttu-id="1a8a8-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1a8a8-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-187">String</span></span>|  
|<span data-ttu-id="1a8a8-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-188">DOMAIN_NAME</span></span>|<span data-ttu-id="1a8a8-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-189">String</span></span>|  
|<span data-ttu-id="1a8a8-190">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-190">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-191">String</span></span>|  
|<span data-ttu-id="1a8a8-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-192">COLUMN_LCID</span></span>|<span data-ttu-id="1a8a8-193">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-193">Int32</span></span>|  
|<span data-ttu-id="1a8a8-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="1a8a8-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="1a8a8-195">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-195">Int32</span></span>|  
|<span data-ttu-id="1a8a8-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-196">COLUMN_SORTID</span></span>|<span data-ttu-id="1a8a8-197">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-197">Int32</span></span>|  
|<span data-ttu-id="1a8a8-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="1a8a8-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="1a8a8-199">Byte[]</span></span>|  
|<span data-ttu-id="1a8a8-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-200">IS_COMPUTED</span></span>|<span data-ttu-id="1a8a8-201">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1a8a8-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1a8a8-202">Procedures</span></span>  
  
|<span data-ttu-id="1a8a8-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-203">ColumnName</span></span>|<span data-ttu-id="1a8a8-204">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1a8a8-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-206">String</span></span>|  
|<span data-ttu-id="1a8a8-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-208">String</span></span>|  
|<span data-ttu-id="1a8a8-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="1a8a8-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-210">String</span></span>|  
|<span data-ttu-id="1a8a8-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1a8a8-212">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-212">Int16</span></span>|  
|<span data-ttu-id="1a8a8-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1a8a8-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-214">String</span></span>|  
|<span data-ttu-id="1a8a8-215">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-215">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-216">String</span></span>|  
|<span data-ttu-id="1a8a8-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-217">DATE_CREATED</span></span>|<span data-ttu-id="1a8a8-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-218">DateTime</span></span>|  
|<span data-ttu-id="1a8a8-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-219">DATE_MODIFIED</span></span>|<span data-ttu-id="1a8a8-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="1a8a8-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1a8a8-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="1a8a8-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-222">ColumnName</span></span>|<span data-ttu-id="1a8a8-223">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1a8a8-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-225">String</span></span>|  
|<span data-ttu-id="1a8a8-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-227">String</span></span>|  
|<span data-ttu-id="1a8a8-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="1a8a8-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-229">String</span></span>|  
|<span data-ttu-id="1a8a8-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-230">PARAMETER_NAME</span></span>|<span data-ttu-id="1a8a8-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-231">String</span></span>|  
|<span data-ttu-id="1a8a8-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="1a8a8-233">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-233">Int32</span></span>|  
|<span data-ttu-id="1a8a8-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="1a8a8-235">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-235">Int32</span></span>|  
|<span data-ttu-id="1a8a8-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1a8a8-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="1a8a8-237">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-237">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1a8a8-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="1a8a8-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-239">String</span></span>|  
|<span data-ttu-id="1a8a8-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-240">IS_NULLABLE</span></span>|<span data-ttu-id="1a8a8-241">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-241">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-242">DATA_TYPE</span></span>|<span data-ttu-id="1a8a8-243">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-243">Int32</span></span>|  
|<span data-ttu-id="1a8a8-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1a8a8-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1a8a8-245">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-245">Int64</span></span>|  
|<span data-ttu-id="1a8a8-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1a8a8-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1a8a8-247">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-247">Int64</span></span>|  
|<span data-ttu-id="1a8a8-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1a8a8-249">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-249">Int32</span></span>|  
|<span data-ttu-id="1a8a8-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="1a8a8-251">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-251">Int16</span></span>|  
|<span data-ttu-id="1a8a8-252">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-252">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-253">String</span></span>|  
|<span data-ttu-id="1a8a8-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-254">TYPE_NAME</span></span>|<span data-ttu-id="1a8a8-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-255">String</span></span>|  
|<span data-ttu-id="1a8a8-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="1a8a8-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="1a8a8-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="1a8a8-258">Catalog</span></span>  
  
|<span data-ttu-id="1a8a8-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-259">ColumnName</span></span>|<span data-ttu-id="1a8a8-260">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-261">CATALOG_NAME</span></span>|<span data-ttu-id="1a8a8-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-262">String</span></span>|  
|<span data-ttu-id="1a8a8-263">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-263">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1a8a8-265">Indizes</span><span class="sxs-lookup"><span data-stu-id="1a8a8-265">Indexes</span></span>  
  
|<span data-ttu-id="1a8a8-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-266">ColumnName</span></span>|<span data-ttu-id="1a8a8-267">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-268">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-269">String</span></span>|  
|<span data-ttu-id="1a8a8-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-271">String</span></span>|  
|<span data-ttu-id="1a8a8-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-272">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-273">String</span></span>|  
|<span data-ttu-id="1a8a8-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-274">INDEX_CATALOG</span></span>|<span data-ttu-id="1a8a8-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-275">String</span></span>|  
|<span data-ttu-id="1a8a8-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="1a8a8-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-277">String</span></span>|  
|<span data-ttu-id="1a8a8-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-278">INDEX_NAME</span></span>|<span data-ttu-id="1a8a8-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-279">String</span></span>|  
|<span data-ttu-id="1a8a8-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1a8a8-280">PRIMARY_KEY</span></span>|<span data-ttu-id="1a8a8-281">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-281">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-282">UNIQUE</span></span>|<span data-ttu-id="1a8a8-283">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-283">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-284">CLUSTERED</span></span>|<span data-ttu-id="1a8a8-285">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-285">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-286">TYPE</span></span>|<span data-ttu-id="1a8a8-287">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-287">Int32</span></span>|  
|<span data-ttu-id="1a8a8-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1a8a8-288">FILL_FACTOR</span></span>|<span data-ttu-id="1a8a8-289">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-289">Int32</span></span>|  
|<span data-ttu-id="1a8a8-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-290">INITIAL_SIZE</span></span>|<span data-ttu-id="1a8a8-291">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-291">Int32</span></span>|  
|<span data-ttu-id="1a8a8-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="1a8a8-292">NULLS</span></span>|<span data-ttu-id="1a8a8-293">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-293">Int32</span></span>|  
|<span data-ttu-id="1a8a8-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1a8a8-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1a8a8-295">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-295">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-296">AUTO_UPDATE</span></span>|<span data-ttu-id="1a8a8-297">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-297">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-298">NULL_COLLATION</span></span>|<span data-ttu-id="1a8a8-299">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-299">Int32</span></span>|  
|<span data-ttu-id="1a8a8-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="1a8a8-301">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-301">Int64</span></span>|  
|<span data-ttu-id="1a8a8-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-302">COLUMN_NAME</span></span>|<span data-ttu-id="1a8a8-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-303">String</span></span>|  
|<span data-ttu-id="1a8a8-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-304">COLUMN_GUID</span></span>|<span data-ttu-id="1a8a8-305">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-305">Guid</span></span>|  
|<span data-ttu-id="1a8a8-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-306">COLUMN_PROPID</span></span>|<span data-ttu-id="1a8a8-307">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-307">Int64</span></span>|  
|<span data-ttu-id="1a8a8-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-308">COLLATION</span></span>|<span data-ttu-id="1a8a8-309">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-309">Int16</span></span>|  
|<span data-ttu-id="1a8a8-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1a8a8-310">CARDINALITY</span></span>|<span data-ttu-id="1a8a8-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="1a8a8-311">Decimal</span></span>|  
|<span data-ttu-id="1a8a8-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="1a8a8-312">PAGES</span></span>|<span data-ttu-id="1a8a8-313">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-313">Int32</span></span>|  
|<span data-ttu-id="1a8a8-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-314">FILTER_CONDITION</span></span>|<span data-ttu-id="1a8a8-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-315">String</span></span>|  
|<span data-ttu-id="1a8a8-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-316">INTEGRATED</span></span>|<span data-ttu-id="1a8a8-317">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="1a8a8-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="1a8a8-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="1a8a8-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="1a8a8-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="1a8a8-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="1a8a8-320">Tables</span></span>  
  
-   <span data-ttu-id="1a8a8-321">Spalten</span><span class="sxs-lookup"><span data-stu-id="1a8a8-321">Columns</span></span>  
  
-   <span data-ttu-id="1a8a8-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1a8a8-322">Procedures</span></span>  
  
-   <span data-ttu-id="1a8a8-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="1a8a8-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="1a8a8-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1a8a8-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="1a8a8-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="1a8a8-325">Views</span></span>  
  
-   <span data-ttu-id="1a8a8-326">Indizes</span><span class="sxs-lookup"><span data-stu-id="1a8a8-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1a8a8-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="1a8a8-327">Tables</span></span>  
  
|<span data-ttu-id="1a8a8-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-328">ColumnName</span></span>|<span data-ttu-id="1a8a8-329">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-330">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-331">String</span></span>|  
|<span data-ttu-id="1a8a8-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-333">String</span></span>|  
|<span data-ttu-id="1a8a8-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-334">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-335">String</span></span>|  
|<span data-ttu-id="1a8a8-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-336">TABLE_TYPE</span></span>|<span data-ttu-id="1a8a8-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-337">String</span></span>|  
|<span data-ttu-id="1a8a8-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-338">TABLE_GUID</span></span>|<span data-ttu-id="1a8a8-339">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-339">Guid</span></span>|  
|<span data-ttu-id="1a8a8-340">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-340">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-341">String</span></span>|  
|<span data-ttu-id="1a8a8-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-342">TABLE_PROPID</span></span>|<span data-ttu-id="1a8a8-343">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-343">Int64</span></span>|  
|<span data-ttu-id="1a8a8-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-344">DATE_CREATED</span></span>|<span data-ttu-id="1a8a8-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-345">DateTime</span></span>|  
|<span data-ttu-id="1a8a8-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-346">DATE_MODIFIED</span></span>|<span data-ttu-id="1a8a8-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1a8a8-348">Spalten</span><span class="sxs-lookup"><span data-stu-id="1a8a8-348">Columns</span></span>  
  
|<span data-ttu-id="1a8a8-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-349">ColumnName</span></span>|<span data-ttu-id="1a8a8-350">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-351">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-352">String</span></span>|  
|<span data-ttu-id="1a8a8-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-354">String</span></span>|  
|<span data-ttu-id="1a8a8-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-355">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-356">String</span></span>|  
|<span data-ttu-id="1a8a8-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-357">COLUMN_NAME</span></span>|<span data-ttu-id="1a8a8-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-358">String</span></span>|  
|<span data-ttu-id="1a8a8-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-359">COLUMN_GUID</span></span>|<span data-ttu-id="1a8a8-360">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-360">Guid</span></span>|  
|<span data-ttu-id="1a8a8-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-361">COLUMN_PROPID</span></span>|<span data-ttu-id="1a8a8-362">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-362">Int64</span></span>|  
|<span data-ttu-id="1a8a8-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="1a8a8-364">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-364">Int64</span></span>|  
|<span data-ttu-id="1a8a8-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1a8a8-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1a8a8-366">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-366">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1a8a8-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1a8a8-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-368">String</span></span>|  
|<span data-ttu-id="1a8a8-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1a8a8-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="1a8a8-370">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-370">Int64</span></span>|  
|<span data-ttu-id="1a8a8-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-371">IS_NULLABLE</span></span>|<span data-ttu-id="1a8a8-372">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-372">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-373">DATA_TYPE</span></span>|<span data-ttu-id="1a8a8-374">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-374">Int32</span></span>|  
|<span data-ttu-id="1a8a8-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-375">TYPE_GUID</span></span>|<span data-ttu-id="1a8a8-376">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-376">Guid</span></span>|  
|<span data-ttu-id="1a8a8-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1a8a8-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1a8a8-378">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-378">Int64</span></span>|  
|<span data-ttu-id="1a8a8-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1a8a8-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1a8a8-380">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-380">Int64</span></span>|  
|<span data-ttu-id="1a8a8-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1a8a8-382">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-382">Int32</span></span>|  
|<span data-ttu-id="1a8a8-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="1a8a8-384">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-384">Int16</span></span>|  
|<span data-ttu-id="1a8a8-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="1a8a8-386">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-386">Int64</span></span>|  
|<span data-ttu-id="1a8a8-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1a8a8-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-388">String</span></span>|  
|<span data-ttu-id="1a8a8-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1a8a8-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-390">String</span></span>|  
|<span data-ttu-id="1a8a8-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1a8a8-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-392">String</span></span>|  
|<span data-ttu-id="1a8a8-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="1a8a8-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-394">String</span></span>|  
|<span data-ttu-id="1a8a8-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1a8a8-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-396">String</span></span>|  
|<span data-ttu-id="1a8a8-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-397">COLLATION_NAME</span></span>|<span data-ttu-id="1a8a8-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-398">String</span></span>|  
|<span data-ttu-id="1a8a8-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1a8a8-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-400">String</span></span>|  
|<span data-ttu-id="1a8a8-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1a8a8-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-402">String</span></span>|  
|<span data-ttu-id="1a8a8-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-403">DOMAIN_NAME</span></span>|<span data-ttu-id="1a8a8-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-404">String</span></span>|  
|<span data-ttu-id="1a8a8-405">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-405">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1a8a8-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1a8a8-407">Procedures</span></span>  
  
|<span data-ttu-id="1a8a8-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-408">ColumnName</span></span>|<span data-ttu-id="1a8a8-409">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1a8a8-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-411">String</span></span>|  
|<span data-ttu-id="1a8a8-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-413">String</span></span>|  
|<span data-ttu-id="1a8a8-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="1a8a8-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-415">String</span></span>|  
|<span data-ttu-id="1a8a8-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1a8a8-417">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-417">Int16</span></span>|  
|<span data-ttu-id="1a8a8-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1a8a8-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-419">String</span></span>|  
|<span data-ttu-id="1a8a8-420">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-420">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-421">String</span></span>|  
|<span data-ttu-id="1a8a8-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-422">DATE_CREATED</span></span>|<span data-ttu-id="1a8a8-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-423">DateTime</span></span>|  
|<span data-ttu-id="1a8a8-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-424">DATE_MODIFIED</span></span>|<span data-ttu-id="1a8a8-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="1a8a8-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="1a8a8-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="1a8a8-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-427">ColumnName</span></span>|<span data-ttu-id="1a8a8-428">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1a8a8-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-430">String</span></span>|  
|<span data-ttu-id="1a8a8-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-432">String</span></span>|  
|<span data-ttu-id="1a8a8-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="1a8a8-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-434">String</span></span>|  
|<span data-ttu-id="1a8a8-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-435">COLUMN_NAME</span></span>|<span data-ttu-id="1a8a8-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-436">String</span></span>|  
|<span data-ttu-id="1a8a8-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-437">COLUMN_GUID</span></span>|<span data-ttu-id="1a8a8-438">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-438">Guid</span></span>|  
|<span data-ttu-id="1a8a8-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-439">COLUMN_PROPID</span></span>|<span data-ttu-id="1a8a8-440">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-440">Int64</span></span>|  
|<span data-ttu-id="1a8a8-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="1a8a8-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="1a8a8-442">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-442">Int64</span></span>|  
|<span data-ttu-id="1a8a8-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="1a8a8-444">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-444">Int64</span></span>|  
|<span data-ttu-id="1a8a8-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-445">IS_NULLABLE</span></span>|<span data-ttu-id="1a8a8-446">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-446">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-447">DATA_TYPE</span></span>|<span data-ttu-id="1a8a8-448">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-448">Int32</span></span>|  
|<span data-ttu-id="1a8a8-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-449">TYPE_GUID</span></span>|<span data-ttu-id="1a8a8-450">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-450">Guid</span></span>|  
|<span data-ttu-id="1a8a8-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1a8a8-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1a8a8-452">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-452">Int64</span></span>|  
|<span data-ttu-id="1a8a8-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1a8a8-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1a8a8-454">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-454">Int64</span></span>|  
|<span data-ttu-id="1a8a8-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1a8a8-456">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-456">Int32</span></span>|  
|<span data-ttu-id="1a8a8-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="1a8a8-458">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-458">Int16</span></span>|  
|<span data-ttu-id="1a8a8-459">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-459">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-460">String</span></span>|  
|<span data-ttu-id="1a8a8-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="1a8a8-461">OVERLOAD</span></span>|<span data-ttu-id="1a8a8-462">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="1a8a8-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="1a8a8-463">Views</span></span>  
  
|<span data-ttu-id="1a8a8-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-464">ColumnName</span></span>|<span data-ttu-id="1a8a8-465">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-466">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-467">String</span></span>|  
|<span data-ttu-id="1a8a8-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-469">String</span></span>|  
|<span data-ttu-id="1a8a8-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-470">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-471">String</span></span>|  
|<span data-ttu-id="1a8a8-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="1a8a8-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-473">String</span></span>|  
|<span data-ttu-id="1a8a8-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-474">CHECK_OPTION</span></span>|<span data-ttu-id="1a8a8-475">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-475">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-476">IS_UPDATABLE</span></span>|<span data-ttu-id="1a8a8-477">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-477">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-478">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-478">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-479">String</span></span>|  
|<span data-ttu-id="1a8a8-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-480">DATE_CREATED</span></span>|<span data-ttu-id="1a8a8-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-481">DateTime</span></span>|  
|<span data-ttu-id="1a8a8-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-482">DATE_MODIFIED</span></span>|<span data-ttu-id="1a8a8-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1a8a8-484">Indizes</span><span class="sxs-lookup"><span data-stu-id="1a8a8-484">Indexes</span></span>  
  
|<span data-ttu-id="1a8a8-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-485">ColumnName</span></span>|<span data-ttu-id="1a8a8-486">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-487">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-488">String</span></span>|  
|<span data-ttu-id="1a8a8-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-490">String</span></span>|  
|<span data-ttu-id="1a8a8-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-491">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-492">String</span></span>|  
|<span data-ttu-id="1a8a8-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-493">INDEX_CATALOG</span></span>|<span data-ttu-id="1a8a8-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-494">String</span></span>|  
|<span data-ttu-id="1a8a8-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="1a8a8-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-496">String</span></span>|  
|<span data-ttu-id="1a8a8-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-497">INDEX_NAME</span></span>|<span data-ttu-id="1a8a8-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-498">String</span></span>|  
|<span data-ttu-id="1a8a8-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1a8a8-499">PRIMARY_KEY</span></span>|<span data-ttu-id="1a8a8-500">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-500">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-501">UNIQUE</span></span>|<span data-ttu-id="1a8a8-502">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-502">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-503">CLUSTERED</span></span>|<span data-ttu-id="1a8a8-504">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-504">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-505">TYPE</span></span>|<span data-ttu-id="1a8a8-506">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-506">Int32</span></span>|  
|<span data-ttu-id="1a8a8-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1a8a8-507">FILL_FACTOR</span></span>|<span data-ttu-id="1a8a8-508">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-508">Int32</span></span>|  
|<span data-ttu-id="1a8a8-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-509">INITIAL_SIZE</span></span>|<span data-ttu-id="1a8a8-510">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-510">Int32</span></span>|  
|<span data-ttu-id="1a8a8-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="1a8a8-511">NULLS</span></span>|<span data-ttu-id="1a8a8-512">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-512">Int32</span></span>|  
|<span data-ttu-id="1a8a8-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1a8a8-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1a8a8-514">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-514">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-515">AUTO_UPDATE</span></span>|<span data-ttu-id="1a8a8-516">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-516">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-517">NULL_COLLATION</span></span>|<span data-ttu-id="1a8a8-518">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-518">Int32</span></span>|  
|<span data-ttu-id="1a8a8-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="1a8a8-520">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-520">Int64</span></span>|  
|<span data-ttu-id="1a8a8-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-521">COLUMN_NAME</span></span>|<span data-ttu-id="1a8a8-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-522">String</span></span>|  
|<span data-ttu-id="1a8a8-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-523">COLUMN_GUID</span></span>|<span data-ttu-id="1a8a8-524">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-524">Guid</span></span>|  
|<span data-ttu-id="1a8a8-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-525">COLUMN_PROPID</span></span>|<span data-ttu-id="1a8a8-526">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-526">Int64</span></span>|  
|<span data-ttu-id="1a8a8-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-527">COLLATION</span></span>|<span data-ttu-id="1a8a8-528">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-528">Int16</span></span>|  
|<span data-ttu-id="1a8a8-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1a8a8-529">CARDINALITY</span></span>|<span data-ttu-id="1a8a8-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="1a8a8-530">Decimal</span></span>|  
|<span data-ttu-id="1a8a8-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="1a8a8-531">PAGES</span></span>|<span data-ttu-id="1a8a8-532">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-532">Int32</span></span>|  
|<span data-ttu-id="1a8a8-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-533">FILTER_CONDITION</span></span>|<span data-ttu-id="1a8a8-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-534">String</span></span>|  
|<span data-ttu-id="1a8a8-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-535">INTEGRATED</span></span>|<span data-ttu-id="1a8a8-536">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="1a8a8-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="1a8a8-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="1a8a8-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="1a8a8-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="1a8a8-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="1a8a8-539">Tables</span></span>  
  
-   <span data-ttu-id="1a8a8-540">Spalten</span><span class="sxs-lookup"><span data-stu-id="1a8a8-540">Columns</span></span>  
  
-   <span data-ttu-id="1a8a8-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1a8a8-541">Procedures</span></span>  
  
-   <span data-ttu-id="1a8a8-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="1a8a8-542">Views</span></span>  
  
-   <span data-ttu-id="1a8a8-543">Indizes</span><span class="sxs-lookup"><span data-stu-id="1a8a8-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="1a8a8-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="1a8a8-544">Tables</span></span>  
  
|<span data-ttu-id="1a8a8-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-545">ColumnName</span></span>|<span data-ttu-id="1a8a8-546">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-547">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-548">String</span></span>|  
|<span data-ttu-id="1a8a8-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-550">String</span></span>|  
|<span data-ttu-id="1a8a8-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-551">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-552">String</span></span>|  
|<span data-ttu-id="1a8a8-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-553">TABLE_TYPE</span></span>|<span data-ttu-id="1a8a8-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-554">String</span></span>|  
|<span data-ttu-id="1a8a8-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-555">TABLE_GUID</span></span>|<span data-ttu-id="1a8a8-556">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-556">Guid</span></span>|  
|<span data-ttu-id="1a8a8-557">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-557">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-558">String</span></span>|  
|<span data-ttu-id="1a8a8-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-559">TABLE_PROPID</span></span>|<span data-ttu-id="1a8a8-560">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-560">Int64</span></span>|  
|<span data-ttu-id="1a8a8-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-561">DATE_CREATED</span></span>|<span data-ttu-id="1a8a8-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-562">DateTime</span></span>|  
|<span data-ttu-id="1a8a8-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-563">DATE_MODIFIED</span></span>|<span data-ttu-id="1a8a8-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1a8a8-565">Spalten</span><span class="sxs-lookup"><span data-stu-id="1a8a8-565">Columns</span></span>  
  
|<span data-ttu-id="1a8a8-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-566">ColumnName</span></span>|<span data-ttu-id="1a8a8-567">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-568">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-569">String</span></span>|  
|<span data-ttu-id="1a8a8-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-571">String</span></span>|  
|<span data-ttu-id="1a8a8-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-572">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-573">String</span></span>|  
|<span data-ttu-id="1a8a8-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-574">COLUMN_NAME</span></span>|<span data-ttu-id="1a8a8-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-575">String</span></span>|  
|<span data-ttu-id="1a8a8-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-576">COLUMN_GUID</span></span>|<span data-ttu-id="1a8a8-577">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-577">Guid</span></span>|  
|<span data-ttu-id="1a8a8-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-578">COLUMN_PROPID</span></span>|<span data-ttu-id="1a8a8-579">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-579">Int64</span></span>|  
|<span data-ttu-id="1a8a8-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="1a8a8-581">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-581">Int64</span></span>|  
|<span data-ttu-id="1a8a8-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="1a8a8-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="1a8a8-583">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-583">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="1a8a8-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="1a8a8-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-585">String</span></span>|  
|<span data-ttu-id="1a8a8-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="1a8a8-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="1a8a8-587">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-587">Int64</span></span>|  
|<span data-ttu-id="1a8a8-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-588">IS_NULLABLE</span></span>|<span data-ttu-id="1a8a8-589">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-589">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-590">DATA_TYPE</span></span>|<span data-ttu-id="1a8a8-591">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-591">Int32</span></span>|  
|<span data-ttu-id="1a8a8-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-592">TYPE_GUID</span></span>|<span data-ttu-id="1a8a8-593">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-593">Guid</span></span>|  
|<span data-ttu-id="1a8a8-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1a8a8-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="1a8a8-595">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-595">Int64</span></span>|  
|<span data-ttu-id="1a8a8-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="1a8a8-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="1a8a8-597">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-597">Int64</span></span>|  
|<span data-ttu-id="1a8a8-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="1a8a8-599">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-599">Int32</span></span>|  
|<span data-ttu-id="1a8a8-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="1a8a8-601">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-601">Int16</span></span>|  
|<span data-ttu-id="1a8a8-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="1a8a8-603">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-603">Int64</span></span>|  
|<span data-ttu-id="1a8a8-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="1a8a8-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-605">String</span></span>|  
|<span data-ttu-id="1a8a8-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="1a8a8-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-607">String</span></span>|  
|<span data-ttu-id="1a8a8-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="1a8a8-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-609">String</span></span>|  
|<span data-ttu-id="1a8a8-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="1a8a8-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-611">String</span></span>|  
|<span data-ttu-id="1a8a8-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="1a8a8-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-613">String</span></span>|  
|<span data-ttu-id="1a8a8-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-614">COLLATION_NAME</span></span>|<span data-ttu-id="1a8a8-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-615">String</span></span>|  
|<span data-ttu-id="1a8a8-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="1a8a8-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-617">String</span></span>|  
|<span data-ttu-id="1a8a8-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="1a8a8-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-619">String</span></span>|  
|<span data-ttu-id="1a8a8-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-620">DOMAIN_NAME</span></span>|<span data-ttu-id="1a8a8-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-621">String</span></span>|  
|<span data-ttu-id="1a8a8-622">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-622">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1a8a8-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="1a8a8-624">Procedures</span></span>  
  
|<span data-ttu-id="1a8a8-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-625">ColumnName</span></span>|<span data-ttu-id="1a8a8-626">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="1a8a8-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-628">String</span></span>|  
|<span data-ttu-id="1a8a8-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-630">String</span></span>|  
|<span data-ttu-id="1a8a8-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="1a8a8-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-632">String</span></span>|  
|<span data-ttu-id="1a8a8-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="1a8a8-634">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-634">Int16</span></span>|  
|<span data-ttu-id="1a8a8-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="1a8a8-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-636">String</span></span>|  
|<span data-ttu-id="1a8a8-637">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-637">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-638">String</span></span>|  
|<span data-ttu-id="1a8a8-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-639">DATE_CREATED</span></span>|<span data-ttu-id="1a8a8-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-640">DateTime</span></span>|  
|<span data-ttu-id="1a8a8-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-641">DATE_MODIFIED</span></span>|<span data-ttu-id="1a8a8-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="1a8a8-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="1a8a8-643">Views</span></span>  
  
|<span data-ttu-id="1a8a8-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-644">ColumnName</span></span>|<span data-ttu-id="1a8a8-645">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-646">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-647">String</span></span>|  
|<span data-ttu-id="1a8a8-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-649">String</span></span>|  
|<span data-ttu-id="1a8a8-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-650">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-651">String</span></span>|  
|<span data-ttu-id="1a8a8-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="1a8a8-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-653">String</span></span>|  
|<span data-ttu-id="1a8a8-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-654">CHECK_OPTION</span></span>|<span data-ttu-id="1a8a8-655">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-655">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-656">IS_UPDATABLE</span></span>|<span data-ttu-id="1a8a8-657">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-657">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-658">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-658">DESCRIPTION</span></span>|<span data-ttu-id="1a8a8-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-659">String</span></span>|  
|<span data-ttu-id="1a8a8-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-660">DATE_CREATED</span></span>|<span data-ttu-id="1a8a8-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-661">DateTime</span></span>|  
|<span data-ttu-id="1a8a8-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-662">DATE_MODIFIED</span></span>|<span data-ttu-id="1a8a8-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="1a8a8-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1a8a8-664">Indizes</span><span class="sxs-lookup"><span data-stu-id="1a8a8-664">Indexes</span></span>  
  
|<span data-ttu-id="1a8a8-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="1a8a8-665">ColumnName</span></span>|<span data-ttu-id="1a8a8-666">DataType</span><span class="sxs-lookup"><span data-stu-id="1a8a8-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="1a8a8-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-667">TABLE_CATALOG</span></span>|<span data-ttu-id="1a8a8-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-668">String</span></span>|  
|<span data-ttu-id="1a8a8-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="1a8a8-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-670">String</span></span>|  
|<span data-ttu-id="1a8a8-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-671">TABLE_NAME</span></span>|<span data-ttu-id="1a8a8-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-672">String</span></span>|  
|<span data-ttu-id="1a8a8-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1a8a8-673">INDEX_CATALOG</span></span>|<span data-ttu-id="1a8a8-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-674">String</span></span>|  
|<span data-ttu-id="1a8a8-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1a8a8-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="1a8a8-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-676">String</span></span>|  
|<span data-ttu-id="1a8a8-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-677">INDEX_NAME</span></span>|<span data-ttu-id="1a8a8-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-678">String</span></span>|  
|<span data-ttu-id="1a8a8-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="1a8a8-679">PRIMARY_KEY</span></span>|<span data-ttu-id="1a8a8-680">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-680">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-681">UNIQUE</span></span>|<span data-ttu-id="1a8a8-682">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-682">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-683">CLUSTERED</span></span>|<span data-ttu-id="1a8a8-684">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-684">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-685">TYPE</span></span>|<span data-ttu-id="1a8a8-686">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-686">Int32</span></span>|  
|<span data-ttu-id="1a8a8-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="1a8a8-687">FILL_FACTOR</span></span>|<span data-ttu-id="1a8a8-688">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-688">Int32</span></span>|  
|<span data-ttu-id="1a8a8-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-689">INITIAL_SIZE</span></span>|<span data-ttu-id="1a8a8-690">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-690">Int32</span></span>|  
|<span data-ttu-id="1a8a8-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="1a8a8-691">NULLS</span></span>|<span data-ttu-id="1a8a8-692">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-692">Int32</span></span>|  
|<span data-ttu-id="1a8a8-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="1a8a8-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="1a8a8-694">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-694">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="1a8a8-695">AUTO_UPDATE</span></span>|<span data-ttu-id="1a8a8-696">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-696">Boolean</span></span>|  
|<span data-ttu-id="1a8a8-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-697">NULL_COLLATION</span></span>|<span data-ttu-id="1a8a8-698">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-698">Int32</span></span>|  
|<span data-ttu-id="1a8a8-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="1a8a8-700">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-700">Int64</span></span>|  
|<span data-ttu-id="1a8a8-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1a8a8-701">COLUMN_NAME</span></span>|<span data-ttu-id="1a8a8-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-702">String</span></span>|  
|<span data-ttu-id="1a8a8-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-703">COLUMN_GUID</span></span>|<span data-ttu-id="1a8a8-704">GUID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-704">Guid</span></span>|  
|<span data-ttu-id="1a8a8-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="1a8a8-705">COLUMN_PROPID</span></span>|<span data-ttu-id="1a8a8-706">Int64</span><span class="sxs-lookup"><span data-stu-id="1a8a8-706">Int64</span></span>|  
|<span data-ttu-id="1a8a8-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-707">COLLATION</span></span>|<span data-ttu-id="1a8a8-708">Int16</span><span class="sxs-lookup"><span data-stu-id="1a8a8-708">Int16</span></span>|  
|<span data-ttu-id="1a8a8-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="1a8a8-709">CARDINALITY</span></span>|<span data-ttu-id="1a8a8-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="1a8a8-710">Decimal</span></span>|  
|<span data-ttu-id="1a8a8-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="1a8a8-711">PAGES</span></span>|<span data-ttu-id="1a8a8-712">Int32</span><span class="sxs-lookup"><span data-stu-id="1a8a8-712">Int32</span></span>|  
|<span data-ttu-id="1a8a8-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="1a8a8-713">FILTER_CONDITION</span></span>|<span data-ttu-id="1a8a8-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1a8a8-714">String</span></span>|  
|<span data-ttu-id="1a8a8-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="1a8a8-715">INTEGRATED</span></span>|<span data-ttu-id="1a8a8-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a8a8-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a8a8-717">See also</span></span>

- [<span data-ttu-id="1a8a8-718">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="1a8a8-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
