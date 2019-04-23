---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164683"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="d5735-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="d5735-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="d5735-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="d5735-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="d5735-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d5735-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="d5735-105">Der Microsoft SQL Server OLE DB-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="d5735-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d5735-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d5735-106">Tables</span></span>  
  
-   <span data-ttu-id="d5735-107">Spalten</span><span class="sxs-lookup"><span data-stu-id="d5735-107">Columns</span></span>  
  
-   <span data-ttu-id="d5735-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d5735-108">Procedures</span></span>  
  
-   <span data-ttu-id="d5735-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d5735-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d5735-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="d5735-110">Catalog</span></span>  
  
-   <span data-ttu-id="d5735-111">Indizes</span><span class="sxs-lookup"><span data-stu-id="d5735-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d5735-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d5735-112">Tables</span></span>  
  
|<span data-ttu-id="d5735-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-113">ColumnName</span></span>|<span data-ttu-id="d5735-114">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-115">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-116">String</span></span>|  
|<span data-ttu-id="d5735-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-118">String</span></span>|  
|<span data-ttu-id="d5735-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-119">TABLE_NAME</span></span>|<span data-ttu-id="d5735-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-120">String</span></span>|  
|<span data-ttu-id="d5735-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-121">TABLE_TYPE</span></span>|<span data-ttu-id="d5735-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-122">String</span></span>|  
|<span data-ttu-id="d5735-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-123">TABLE_GUID</span></span>|<span data-ttu-id="d5735-124">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-124">Guid</span></span>|  
|<span data-ttu-id="d5735-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-125">DESCRIPTION</span></span>|<span data-ttu-id="d5735-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-126">String</span></span>|  
|<span data-ttu-id="d5735-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d5735-127">TABLE_PROPID</span></span>|<span data-ttu-id="d5735-128">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-128">Int64</span></span>|  
|<span data-ttu-id="d5735-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d5735-129">DATE_CREATED</span></span>|<span data-ttu-id="d5735-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-130">DateTime</span></span>|  
|<span data-ttu-id="d5735-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d5735-131">DATE_MODIFIED</span></span>|<span data-ttu-id="d5735-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d5735-133">Spalten</span><span class="sxs-lookup"><span data-stu-id="d5735-133">Columns</span></span>  
  
|<span data-ttu-id="d5735-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-134">ColumnName</span></span>|<span data-ttu-id="d5735-135">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-136">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-137">String</span></span>|  
|<span data-ttu-id="d5735-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-139">String</span></span>|  
|<span data-ttu-id="d5735-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-140">TABLE_NAME</span></span>|<span data-ttu-id="d5735-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-141">String</span></span>|  
|<span data-ttu-id="d5735-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-142">COLUMN_NAME</span></span>|<span data-ttu-id="d5735-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-143">String</span></span>|  
|<span data-ttu-id="d5735-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-144">COLUMN_GUID</span></span>|<span data-ttu-id="d5735-145">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-145">Guid</span></span>|  
|<span data-ttu-id="d5735-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d5735-146">COLUMN_PROPID</span></span>|<span data-ttu-id="d5735-147">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-147">Int64</span></span>|  
|<span data-ttu-id="d5735-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d5735-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="d5735-149">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-149">Int64</span></span>|  
|<span data-ttu-id="d5735-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d5735-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d5735-151">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-151">Boolean</span></span>|  
|<span data-ttu-id="d5735-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d5735-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d5735-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-153">String</span></span>|  
|<span data-ttu-id="d5735-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d5735-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="d5735-155">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-155">Int64</span></span>|  
|<span data-ttu-id="d5735-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d5735-156">IS_NULLABLE</span></span>|<span data-ttu-id="d5735-157">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-157">Boolean</span></span>|  
|<span data-ttu-id="d5735-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-158">DATA_TYPE</span></span>|<span data-ttu-id="d5735-159">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-159">Int32</span></span>|  
|<span data-ttu-id="d5735-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-160">TYPE_GUID</span></span>|<span data-ttu-id="d5735-161">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-161">Guid</span></span>|  
|<span data-ttu-id="d5735-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d5735-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d5735-163">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-163">Int64</span></span>|  
|<span data-ttu-id="d5735-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d5735-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d5735-165">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-165">Int64</span></span>|  
|<span data-ttu-id="d5735-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d5735-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d5735-167">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-167">Int32</span></span>|  
|<span data-ttu-id="d5735-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d5735-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="d5735-169">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-169">Int16</span></span>|  
|<span data-ttu-id="d5735-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d5735-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="d5735-171">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-171">Int64</span></span>|  
|<span data-ttu-id="d5735-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d5735-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-173">String</span></span>|  
|<span data-ttu-id="d5735-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d5735-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-175">String</span></span>|  
|<span data-ttu-id="d5735-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d5735-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-177">String</span></span>|  
|<span data-ttu-id="d5735-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="d5735-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-179">String</span></span>|  
|<span data-ttu-id="d5735-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d5735-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-181">String</span></span>|  
|<span data-ttu-id="d5735-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-182">COLLATION_NAME</span></span>|<span data-ttu-id="d5735-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-183">String</span></span>|  
|<span data-ttu-id="d5735-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d5735-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-185">String</span></span>|  
|<span data-ttu-id="d5735-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d5735-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-187">String</span></span>|  
|<span data-ttu-id="d5735-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-188">DOMAIN_NAME</span></span>|<span data-ttu-id="d5735-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-189">String</span></span>|  
|<span data-ttu-id="d5735-190">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-190">DESCRIPTION</span></span>|<span data-ttu-id="d5735-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-191">String</span></span>|  
|<span data-ttu-id="d5735-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="d5735-192">COLUMN_LCID</span></span>|<span data-ttu-id="d5735-193">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-193">Int32</span></span>|  
|<span data-ttu-id="d5735-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="d5735-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="d5735-195">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-195">Int32</span></span>|  
|<span data-ttu-id="d5735-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="d5735-196">COLUMN_SORTID</span></span>|<span data-ttu-id="d5735-197">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-197">Int32</span></span>|  
|<span data-ttu-id="d5735-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="d5735-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="d5735-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="d5735-199">Byte[]</span></span>|  
|<span data-ttu-id="d5735-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="d5735-200">IS_COMPUTED</span></span>|<span data-ttu-id="d5735-201">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d5735-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d5735-202">Procedures</span></span>  
  
|<span data-ttu-id="d5735-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-203">ColumnName</span></span>|<span data-ttu-id="d5735-204">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d5735-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-206">String</span></span>|  
|<span data-ttu-id="d5735-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d5735-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-208">String</span></span>|  
|<span data-ttu-id="d5735-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="d5735-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-210">String</span></span>|  
|<span data-ttu-id="d5735-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d5735-212">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-212">Int16</span></span>|  
|<span data-ttu-id="d5735-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d5735-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d5735-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-214">String</span></span>|  
|<span data-ttu-id="d5735-215">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-215">DESCRIPTION</span></span>|<span data-ttu-id="d5735-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-216">String</span></span>|  
|<span data-ttu-id="d5735-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d5735-217">DATE_CREATED</span></span>|<span data-ttu-id="d5735-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-218">DateTime</span></span>|  
|<span data-ttu-id="d5735-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d5735-219">DATE_MODIFIED</span></span>|<span data-ttu-id="d5735-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d5735-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d5735-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d5735-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-222">ColumnName</span></span>|<span data-ttu-id="d5735-223">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d5735-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-225">String</span></span>|  
|<span data-ttu-id="d5735-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d5735-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-227">String</span></span>|  
|<span data-ttu-id="d5735-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="d5735-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-229">String</span></span>|  
|<span data-ttu-id="d5735-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-230">PARAMETER_NAME</span></span>|<span data-ttu-id="d5735-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-231">String</span></span>|  
|<span data-ttu-id="d5735-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d5735-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="d5735-233">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-233">Int32</span></span>|  
|<span data-ttu-id="d5735-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="d5735-235">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-235">Int32</span></span>|  
|<span data-ttu-id="d5735-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d5735-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="d5735-237">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-237">Boolean</span></span>|  
|<span data-ttu-id="d5735-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d5735-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="d5735-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-239">String</span></span>|  
|<span data-ttu-id="d5735-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d5735-240">IS_NULLABLE</span></span>|<span data-ttu-id="d5735-241">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-241">Boolean</span></span>|  
|<span data-ttu-id="d5735-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-242">DATA_TYPE</span></span>|<span data-ttu-id="d5735-243">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-243">Int32</span></span>|  
|<span data-ttu-id="d5735-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d5735-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d5735-245">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-245">Int64</span></span>|  
|<span data-ttu-id="d5735-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d5735-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d5735-247">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-247">Int64</span></span>|  
|<span data-ttu-id="d5735-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d5735-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d5735-249">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-249">Int32</span></span>|  
|<span data-ttu-id="d5735-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d5735-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="d5735-251">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-251">Int16</span></span>|  
|<span data-ttu-id="d5735-252">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-252">DESCRIPTION</span></span>|<span data-ttu-id="d5735-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-253">String</span></span>|  
|<span data-ttu-id="d5735-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-254">TYPE_NAME</span></span>|<span data-ttu-id="d5735-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-255">String</span></span>|  
|<span data-ttu-id="d5735-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="d5735-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="d5735-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="d5735-258">Catalog</span></span>  
  
|<span data-ttu-id="d5735-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-259">ColumnName</span></span>|<span data-ttu-id="d5735-260">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-261">CATALOG_NAME</span></span>|<span data-ttu-id="d5735-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-262">String</span></span>|  
|<span data-ttu-id="d5735-263">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-263">DESCRIPTION</span></span>|<span data-ttu-id="d5735-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d5735-265">Indizes</span><span class="sxs-lookup"><span data-stu-id="d5735-265">Indexes</span></span>  
  
|<span data-ttu-id="d5735-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-266">ColumnName</span></span>|<span data-ttu-id="d5735-267">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-268">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-269">String</span></span>|  
|<span data-ttu-id="d5735-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-271">String</span></span>|  
|<span data-ttu-id="d5735-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-272">TABLE_NAME</span></span>|<span data-ttu-id="d5735-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-273">String</span></span>|  
|<span data-ttu-id="d5735-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-274">INDEX_CATALOG</span></span>|<span data-ttu-id="d5735-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-275">String</span></span>|  
|<span data-ttu-id="d5735-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="d5735-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-277">String</span></span>|  
|<span data-ttu-id="d5735-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-278">INDEX_NAME</span></span>|<span data-ttu-id="d5735-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-279">String</span></span>|  
|<span data-ttu-id="d5735-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d5735-280">PRIMARY_KEY</span></span>|<span data-ttu-id="d5735-281">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-281">Boolean</span></span>|  
|<span data-ttu-id="d5735-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d5735-282">UNIQUE</span></span>|<span data-ttu-id="d5735-283">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-283">Boolean</span></span>|  
|<span data-ttu-id="d5735-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d5735-284">CLUSTERED</span></span>|<span data-ttu-id="d5735-285">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-285">Boolean</span></span>|  
|<span data-ttu-id="d5735-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-286">TYPE</span></span>|<span data-ttu-id="d5735-287">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-287">Int32</span></span>|  
|<span data-ttu-id="d5735-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d5735-288">FILL_FACTOR</span></span>|<span data-ttu-id="d5735-289">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-289">Int32</span></span>|  
|<span data-ttu-id="d5735-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d5735-290">INITIAL_SIZE</span></span>|<span data-ttu-id="d5735-291">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-291">Int32</span></span>|  
|<span data-ttu-id="d5735-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="d5735-292">NULLS</span></span>|<span data-ttu-id="d5735-293">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-293">Int32</span></span>|  
|<span data-ttu-id="d5735-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d5735-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d5735-295">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-295">Boolean</span></span>|  
|<span data-ttu-id="d5735-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d5735-296">AUTO_UPDATE</span></span>|<span data-ttu-id="d5735-297">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-297">Boolean</span></span>|  
|<span data-ttu-id="d5735-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d5735-298">NULL_COLLATION</span></span>|<span data-ttu-id="d5735-299">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-299">Int32</span></span>|  
|<span data-ttu-id="d5735-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d5735-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="d5735-301">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-301">Int64</span></span>|  
|<span data-ttu-id="d5735-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-302">COLUMN_NAME</span></span>|<span data-ttu-id="d5735-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-303">String</span></span>|  
|<span data-ttu-id="d5735-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-304">COLUMN_GUID</span></span>|<span data-ttu-id="d5735-305">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-305">Guid</span></span>|  
|<span data-ttu-id="d5735-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d5735-306">COLUMN_PROPID</span></span>|<span data-ttu-id="d5735-307">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-307">Int64</span></span>|  
|<span data-ttu-id="d5735-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d5735-308">COLLATION</span></span>|<span data-ttu-id="d5735-309">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-309">Int16</span></span>|  
|<span data-ttu-id="d5735-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d5735-310">CARDINALITY</span></span>|<span data-ttu-id="d5735-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="d5735-311">Decimal</span></span>|  
|<span data-ttu-id="d5735-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="d5735-312">PAGES</span></span>|<span data-ttu-id="d5735-313">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-313">Int32</span></span>|  
|<span data-ttu-id="d5735-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d5735-314">FILTER_CONDITION</span></span>|<span data-ttu-id="d5735-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-315">String</span></span>|  
|<span data-ttu-id="d5735-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d5735-316">INTEGRATED</span></span>|<span data-ttu-id="d5735-317">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="d5735-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d5735-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="d5735-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="d5735-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d5735-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d5735-320">Tables</span></span>  
  
-   <span data-ttu-id="d5735-321">Spalten</span><span class="sxs-lookup"><span data-stu-id="d5735-321">Columns</span></span>  
  
-   <span data-ttu-id="d5735-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d5735-322">Procedures</span></span>  
  
-   <span data-ttu-id="d5735-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d5735-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="d5735-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d5735-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="d5735-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="d5735-325">Views</span></span>  
  
-   <span data-ttu-id="d5735-326">Indizes</span><span class="sxs-lookup"><span data-stu-id="d5735-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d5735-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d5735-327">Tables</span></span>  
  
|<span data-ttu-id="d5735-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-328">ColumnName</span></span>|<span data-ttu-id="d5735-329">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-330">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-331">String</span></span>|  
|<span data-ttu-id="d5735-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-333">String</span></span>|  
|<span data-ttu-id="d5735-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-334">TABLE_NAME</span></span>|<span data-ttu-id="d5735-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-335">String</span></span>|  
|<span data-ttu-id="d5735-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-336">TABLE_TYPE</span></span>|<span data-ttu-id="d5735-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-337">String</span></span>|  
|<span data-ttu-id="d5735-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-338">TABLE_GUID</span></span>|<span data-ttu-id="d5735-339">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-339">Guid</span></span>|  
|<span data-ttu-id="d5735-340">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-340">DESCRIPTION</span></span>|<span data-ttu-id="d5735-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-341">String</span></span>|  
|<span data-ttu-id="d5735-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d5735-342">TABLE_PROPID</span></span>|<span data-ttu-id="d5735-343">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-343">Int64</span></span>|  
|<span data-ttu-id="d5735-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d5735-344">DATE_CREATED</span></span>|<span data-ttu-id="d5735-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-345">DateTime</span></span>|  
|<span data-ttu-id="d5735-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d5735-346">DATE_MODIFIED</span></span>|<span data-ttu-id="d5735-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d5735-348">Spalten</span><span class="sxs-lookup"><span data-stu-id="d5735-348">Columns</span></span>  
  
|<span data-ttu-id="d5735-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-349">ColumnName</span></span>|<span data-ttu-id="d5735-350">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-351">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-352">String</span></span>|  
|<span data-ttu-id="d5735-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-354">String</span></span>|  
|<span data-ttu-id="d5735-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-355">TABLE_NAME</span></span>|<span data-ttu-id="d5735-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-356">String</span></span>|  
|<span data-ttu-id="d5735-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-357">COLUMN_NAME</span></span>|<span data-ttu-id="d5735-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-358">String</span></span>|  
|<span data-ttu-id="d5735-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-359">COLUMN_GUID</span></span>|<span data-ttu-id="d5735-360">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-360">Guid</span></span>|  
|<span data-ttu-id="d5735-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d5735-361">COLUMN_PROPID</span></span>|<span data-ttu-id="d5735-362">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-362">Int64</span></span>|  
|<span data-ttu-id="d5735-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d5735-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="d5735-364">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-364">Int64</span></span>|  
|<span data-ttu-id="d5735-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d5735-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d5735-366">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-366">Boolean</span></span>|  
|<span data-ttu-id="d5735-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d5735-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d5735-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-368">String</span></span>|  
|<span data-ttu-id="d5735-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d5735-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="d5735-370">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-370">Int64</span></span>|  
|<span data-ttu-id="d5735-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d5735-371">IS_NULLABLE</span></span>|<span data-ttu-id="d5735-372">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-372">Boolean</span></span>|  
|<span data-ttu-id="d5735-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-373">DATA_TYPE</span></span>|<span data-ttu-id="d5735-374">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-374">Int32</span></span>|  
|<span data-ttu-id="d5735-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-375">TYPE_GUID</span></span>|<span data-ttu-id="d5735-376">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-376">Guid</span></span>|  
|<span data-ttu-id="d5735-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d5735-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d5735-378">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-378">Int64</span></span>|  
|<span data-ttu-id="d5735-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d5735-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d5735-380">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-380">Int64</span></span>|  
|<span data-ttu-id="d5735-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d5735-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d5735-382">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-382">Int32</span></span>|  
|<span data-ttu-id="d5735-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d5735-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="d5735-384">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-384">Int16</span></span>|  
|<span data-ttu-id="d5735-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d5735-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="d5735-386">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-386">Int64</span></span>|  
|<span data-ttu-id="d5735-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d5735-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-388">String</span></span>|  
|<span data-ttu-id="d5735-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d5735-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-390">String</span></span>|  
|<span data-ttu-id="d5735-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d5735-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-392">String</span></span>|  
|<span data-ttu-id="d5735-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="d5735-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-394">String</span></span>|  
|<span data-ttu-id="d5735-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d5735-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-396">String</span></span>|  
|<span data-ttu-id="d5735-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-397">COLLATION_NAME</span></span>|<span data-ttu-id="d5735-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-398">String</span></span>|  
|<span data-ttu-id="d5735-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d5735-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-400">String</span></span>|  
|<span data-ttu-id="d5735-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d5735-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-402">String</span></span>|  
|<span data-ttu-id="d5735-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-403">DOMAIN_NAME</span></span>|<span data-ttu-id="d5735-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-404">String</span></span>|  
|<span data-ttu-id="d5735-405">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-405">DESCRIPTION</span></span>|<span data-ttu-id="d5735-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d5735-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d5735-407">Procedures</span></span>  
  
|<span data-ttu-id="d5735-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-408">ColumnName</span></span>|<span data-ttu-id="d5735-409">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d5735-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-411">String</span></span>|  
|<span data-ttu-id="d5735-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d5735-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-413">String</span></span>|  
|<span data-ttu-id="d5735-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="d5735-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-415">String</span></span>|  
|<span data-ttu-id="d5735-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d5735-417">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-417">Int16</span></span>|  
|<span data-ttu-id="d5735-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d5735-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d5735-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-419">String</span></span>|  
|<span data-ttu-id="d5735-420">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-420">DESCRIPTION</span></span>|<span data-ttu-id="d5735-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-421">String</span></span>|  
|<span data-ttu-id="d5735-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d5735-422">DATE_CREATED</span></span>|<span data-ttu-id="d5735-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-423">DateTime</span></span>|  
|<span data-ttu-id="d5735-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d5735-424">DATE_MODIFIED</span></span>|<span data-ttu-id="d5735-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="d5735-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="d5735-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="d5735-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-427">ColumnName</span></span>|<span data-ttu-id="d5735-428">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d5735-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-430">String</span></span>|  
|<span data-ttu-id="d5735-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d5735-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-432">String</span></span>|  
|<span data-ttu-id="d5735-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="d5735-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-434">String</span></span>|  
|<span data-ttu-id="d5735-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-435">COLUMN_NAME</span></span>|<span data-ttu-id="d5735-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-436">String</span></span>|  
|<span data-ttu-id="d5735-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-437">COLUMN_GUID</span></span>|<span data-ttu-id="d5735-438">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-438">Guid</span></span>|  
|<span data-ttu-id="d5735-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d5735-439">COLUMN_PROPID</span></span>|<span data-ttu-id="d5735-440">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-440">Int64</span></span>|  
|<span data-ttu-id="d5735-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="d5735-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="d5735-442">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-442">Int64</span></span>|  
|<span data-ttu-id="d5735-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d5735-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="d5735-444">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-444">Int64</span></span>|  
|<span data-ttu-id="d5735-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d5735-445">IS_NULLABLE</span></span>|<span data-ttu-id="d5735-446">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-446">Boolean</span></span>|  
|<span data-ttu-id="d5735-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-447">DATA_TYPE</span></span>|<span data-ttu-id="d5735-448">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-448">Int32</span></span>|  
|<span data-ttu-id="d5735-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-449">TYPE_GUID</span></span>|<span data-ttu-id="d5735-450">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-450">Guid</span></span>|  
|<span data-ttu-id="d5735-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d5735-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d5735-452">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-452">Int64</span></span>|  
|<span data-ttu-id="d5735-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d5735-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d5735-454">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-454">Int64</span></span>|  
|<span data-ttu-id="d5735-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d5735-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d5735-456">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-456">Int32</span></span>|  
|<span data-ttu-id="d5735-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d5735-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="d5735-458">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-458">Int16</span></span>|  
|<span data-ttu-id="d5735-459">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-459">DESCRIPTION</span></span>|<span data-ttu-id="d5735-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-460">String</span></span>|  
|<span data-ttu-id="d5735-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="d5735-461">OVERLOAD</span></span>|<span data-ttu-id="d5735-462">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d5735-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="d5735-463">Views</span></span>  
  
|<span data-ttu-id="d5735-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-464">ColumnName</span></span>|<span data-ttu-id="d5735-465">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-466">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-467">String</span></span>|  
|<span data-ttu-id="d5735-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-469">String</span></span>|  
|<span data-ttu-id="d5735-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-470">TABLE_NAME</span></span>|<span data-ttu-id="d5735-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-471">String</span></span>|  
|<span data-ttu-id="d5735-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d5735-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="d5735-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-473">String</span></span>|  
|<span data-ttu-id="d5735-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="d5735-474">CHECK_OPTION</span></span>|<span data-ttu-id="d5735-475">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-475">Boolean</span></span>|  
|<span data-ttu-id="d5735-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="d5735-476">IS_UPDATABLE</span></span>|<span data-ttu-id="d5735-477">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-477">Boolean</span></span>|  
|<span data-ttu-id="d5735-478">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-478">DESCRIPTION</span></span>|<span data-ttu-id="d5735-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-479">String</span></span>|  
|<span data-ttu-id="d5735-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d5735-480">DATE_CREATED</span></span>|<span data-ttu-id="d5735-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-481">DateTime</span></span>|  
|<span data-ttu-id="d5735-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d5735-482">DATE_MODIFIED</span></span>|<span data-ttu-id="d5735-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d5735-484">Indizes</span><span class="sxs-lookup"><span data-stu-id="d5735-484">Indexes</span></span>  
  
|<span data-ttu-id="d5735-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-485">ColumnName</span></span>|<span data-ttu-id="d5735-486">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-487">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-488">String</span></span>|  
|<span data-ttu-id="d5735-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-490">String</span></span>|  
|<span data-ttu-id="d5735-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-491">TABLE_NAME</span></span>|<span data-ttu-id="d5735-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-492">String</span></span>|  
|<span data-ttu-id="d5735-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-493">INDEX_CATALOG</span></span>|<span data-ttu-id="d5735-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-494">String</span></span>|  
|<span data-ttu-id="d5735-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="d5735-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-496">String</span></span>|  
|<span data-ttu-id="d5735-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-497">INDEX_NAME</span></span>|<span data-ttu-id="d5735-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-498">String</span></span>|  
|<span data-ttu-id="d5735-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d5735-499">PRIMARY_KEY</span></span>|<span data-ttu-id="d5735-500">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-500">Boolean</span></span>|  
|<span data-ttu-id="d5735-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d5735-501">UNIQUE</span></span>|<span data-ttu-id="d5735-502">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-502">Boolean</span></span>|  
|<span data-ttu-id="d5735-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d5735-503">CLUSTERED</span></span>|<span data-ttu-id="d5735-504">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-504">Boolean</span></span>|  
|<span data-ttu-id="d5735-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-505">TYPE</span></span>|<span data-ttu-id="d5735-506">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-506">Int32</span></span>|  
|<span data-ttu-id="d5735-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d5735-507">FILL_FACTOR</span></span>|<span data-ttu-id="d5735-508">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-508">Int32</span></span>|  
|<span data-ttu-id="d5735-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d5735-509">INITIAL_SIZE</span></span>|<span data-ttu-id="d5735-510">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-510">Int32</span></span>|  
|<span data-ttu-id="d5735-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="d5735-511">NULLS</span></span>|<span data-ttu-id="d5735-512">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-512">Int32</span></span>|  
|<span data-ttu-id="d5735-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d5735-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d5735-514">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-514">Boolean</span></span>|  
|<span data-ttu-id="d5735-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d5735-515">AUTO_UPDATE</span></span>|<span data-ttu-id="d5735-516">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-516">Boolean</span></span>|  
|<span data-ttu-id="d5735-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d5735-517">NULL_COLLATION</span></span>|<span data-ttu-id="d5735-518">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-518">Int32</span></span>|  
|<span data-ttu-id="d5735-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d5735-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="d5735-520">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-520">Int64</span></span>|  
|<span data-ttu-id="d5735-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-521">COLUMN_NAME</span></span>|<span data-ttu-id="d5735-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-522">String</span></span>|  
|<span data-ttu-id="d5735-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-523">COLUMN_GUID</span></span>|<span data-ttu-id="d5735-524">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-524">Guid</span></span>|  
|<span data-ttu-id="d5735-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d5735-525">COLUMN_PROPID</span></span>|<span data-ttu-id="d5735-526">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-526">Int64</span></span>|  
|<span data-ttu-id="d5735-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d5735-527">COLLATION</span></span>|<span data-ttu-id="d5735-528">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-528">Int16</span></span>|  
|<span data-ttu-id="d5735-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d5735-529">CARDINALITY</span></span>|<span data-ttu-id="d5735-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="d5735-530">Decimal</span></span>|  
|<span data-ttu-id="d5735-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="d5735-531">PAGES</span></span>|<span data-ttu-id="d5735-532">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-532">Int32</span></span>|  
|<span data-ttu-id="d5735-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d5735-533">FILTER_CONDITION</span></span>|<span data-ttu-id="d5735-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-534">String</span></span>|  
|<span data-ttu-id="d5735-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d5735-535">INTEGRATED</span></span>|<span data-ttu-id="d5735-536">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="d5735-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="d5735-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="d5735-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="d5735-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="d5735-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d5735-539">Tables</span></span>  
  
-   <span data-ttu-id="d5735-540">Spalten</span><span class="sxs-lookup"><span data-stu-id="d5735-540">Columns</span></span>  
  
-   <span data-ttu-id="d5735-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d5735-541">Procedures</span></span>  
  
-   <span data-ttu-id="d5735-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="d5735-542">Views</span></span>  
  
-   <span data-ttu-id="d5735-543">Indizes</span><span class="sxs-lookup"><span data-stu-id="d5735-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="d5735-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="d5735-544">Tables</span></span>  
  
|<span data-ttu-id="d5735-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-545">ColumnName</span></span>|<span data-ttu-id="d5735-546">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-547">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-548">String</span></span>|  
|<span data-ttu-id="d5735-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-550">String</span></span>|  
|<span data-ttu-id="d5735-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-551">TABLE_NAME</span></span>|<span data-ttu-id="d5735-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-552">String</span></span>|  
|<span data-ttu-id="d5735-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-553">TABLE_TYPE</span></span>|<span data-ttu-id="d5735-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-554">String</span></span>|  
|<span data-ttu-id="d5735-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-555">TABLE_GUID</span></span>|<span data-ttu-id="d5735-556">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-556">Guid</span></span>|  
|<span data-ttu-id="d5735-557">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-557">DESCRIPTION</span></span>|<span data-ttu-id="d5735-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-558">String</span></span>|  
|<span data-ttu-id="d5735-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="d5735-559">TABLE_PROPID</span></span>|<span data-ttu-id="d5735-560">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-560">Int64</span></span>|  
|<span data-ttu-id="d5735-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d5735-561">DATE_CREATED</span></span>|<span data-ttu-id="d5735-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-562">DateTime</span></span>|  
|<span data-ttu-id="d5735-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d5735-563">DATE_MODIFIED</span></span>|<span data-ttu-id="d5735-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d5735-565">Spalten</span><span class="sxs-lookup"><span data-stu-id="d5735-565">Columns</span></span>  
  
|<span data-ttu-id="d5735-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-566">ColumnName</span></span>|<span data-ttu-id="d5735-567">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-568">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-569">String</span></span>|  
|<span data-ttu-id="d5735-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-571">String</span></span>|  
|<span data-ttu-id="d5735-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-572">TABLE_NAME</span></span>|<span data-ttu-id="d5735-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-573">String</span></span>|  
|<span data-ttu-id="d5735-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-574">COLUMN_NAME</span></span>|<span data-ttu-id="d5735-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-575">String</span></span>|  
|<span data-ttu-id="d5735-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-576">COLUMN_GUID</span></span>|<span data-ttu-id="d5735-577">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-577">Guid</span></span>|  
|<span data-ttu-id="d5735-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d5735-578">COLUMN_PROPID</span></span>|<span data-ttu-id="d5735-579">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-579">Int64</span></span>|  
|<span data-ttu-id="d5735-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d5735-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="d5735-581">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-581">Int64</span></span>|  
|<span data-ttu-id="d5735-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="d5735-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="d5735-583">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-583">Boolean</span></span>|  
|<span data-ttu-id="d5735-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d5735-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="d5735-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-585">String</span></span>|  
|<span data-ttu-id="d5735-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d5735-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="d5735-587">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-587">Int64</span></span>|  
|<span data-ttu-id="d5735-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="d5735-588">IS_NULLABLE</span></span>|<span data-ttu-id="d5735-589">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-589">Boolean</span></span>|  
|<span data-ttu-id="d5735-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-590">DATA_TYPE</span></span>|<span data-ttu-id="d5735-591">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-591">Int32</span></span>|  
|<span data-ttu-id="d5735-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-592">TYPE_GUID</span></span>|<span data-ttu-id="d5735-593">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-593">Guid</span></span>|  
|<span data-ttu-id="d5735-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d5735-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="d5735-595">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-595">Int64</span></span>|  
|<span data-ttu-id="d5735-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="d5735-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="d5735-597">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-597">Int64</span></span>|  
|<span data-ttu-id="d5735-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d5735-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="d5735-599">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-599">Int32</span></span>|  
|<span data-ttu-id="d5735-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="d5735-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="d5735-601">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-601">Int16</span></span>|  
|<span data-ttu-id="d5735-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="d5735-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="d5735-603">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-603">Int64</span></span>|  
|<span data-ttu-id="d5735-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="d5735-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-605">String</span></span>|  
|<span data-ttu-id="d5735-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="d5735-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-607">String</span></span>|  
|<span data-ttu-id="d5735-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="d5735-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-609">String</span></span>|  
|<span data-ttu-id="d5735-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="d5735-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-611">String</span></span>|  
|<span data-ttu-id="d5735-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="d5735-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-613">String</span></span>|  
|<span data-ttu-id="d5735-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-614">COLLATION_NAME</span></span>|<span data-ttu-id="d5735-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-615">String</span></span>|  
|<span data-ttu-id="d5735-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="d5735-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-617">String</span></span>|  
|<span data-ttu-id="d5735-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="d5735-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-619">String</span></span>|  
|<span data-ttu-id="d5735-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-620">DOMAIN_NAME</span></span>|<span data-ttu-id="d5735-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-621">String</span></span>|  
|<span data-ttu-id="d5735-622">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-622">DESCRIPTION</span></span>|<span data-ttu-id="d5735-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d5735-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d5735-624">Procedures</span></span>  
  
|<span data-ttu-id="d5735-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-625">ColumnName</span></span>|<span data-ttu-id="d5735-626">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="d5735-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-628">String</span></span>|  
|<span data-ttu-id="d5735-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="d5735-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-630">String</span></span>|  
|<span data-ttu-id="d5735-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="d5735-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-632">String</span></span>|  
|<span data-ttu-id="d5735-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="d5735-634">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-634">Int16</span></span>|  
|<span data-ttu-id="d5735-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d5735-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="d5735-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-636">String</span></span>|  
|<span data-ttu-id="d5735-637">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-637">DESCRIPTION</span></span>|<span data-ttu-id="d5735-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-638">String</span></span>|  
|<span data-ttu-id="d5735-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d5735-639">DATE_CREATED</span></span>|<span data-ttu-id="d5735-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-640">DateTime</span></span>|  
|<span data-ttu-id="d5735-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d5735-641">DATE_MODIFIED</span></span>|<span data-ttu-id="d5735-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d5735-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="d5735-643">Views</span></span>  
  
|<span data-ttu-id="d5735-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-644">ColumnName</span></span>|<span data-ttu-id="d5735-645">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-646">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-647">String</span></span>|  
|<span data-ttu-id="d5735-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-649">String</span></span>|  
|<span data-ttu-id="d5735-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-650">TABLE_NAME</span></span>|<span data-ttu-id="d5735-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-651">String</span></span>|  
|<span data-ttu-id="d5735-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="d5735-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="d5735-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-653">String</span></span>|  
|<span data-ttu-id="d5735-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="d5735-654">CHECK_OPTION</span></span>|<span data-ttu-id="d5735-655">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-655">Boolean</span></span>|  
|<span data-ttu-id="d5735-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="d5735-656">IS_UPDATABLE</span></span>|<span data-ttu-id="d5735-657">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-657">Boolean</span></span>|  
|<span data-ttu-id="d5735-658">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d5735-658">DESCRIPTION</span></span>|<span data-ttu-id="d5735-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-659">String</span></span>|  
|<span data-ttu-id="d5735-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="d5735-660">DATE_CREATED</span></span>|<span data-ttu-id="d5735-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-661">DateTime</span></span>|  
|<span data-ttu-id="d5735-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="d5735-662">DATE_MODIFIED</span></span>|<span data-ttu-id="d5735-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="d5735-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d5735-664">Indizes</span><span class="sxs-lookup"><span data-stu-id="d5735-664">Indexes</span></span>  
  
|<span data-ttu-id="d5735-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d5735-665">ColumnName</span></span>|<span data-ttu-id="d5735-666">DataType</span><span class="sxs-lookup"><span data-stu-id="d5735-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="d5735-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-667">TABLE_CATALOG</span></span>|<span data-ttu-id="d5735-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-668">String</span></span>|  
|<span data-ttu-id="d5735-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="d5735-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-670">String</span></span>|  
|<span data-ttu-id="d5735-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-671">TABLE_NAME</span></span>|<span data-ttu-id="d5735-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-672">String</span></span>|  
|<span data-ttu-id="d5735-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d5735-673">INDEX_CATALOG</span></span>|<span data-ttu-id="d5735-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-674">String</span></span>|  
|<span data-ttu-id="d5735-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d5735-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="d5735-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-676">String</span></span>|  
|<span data-ttu-id="d5735-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-677">INDEX_NAME</span></span>|<span data-ttu-id="d5735-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-678">String</span></span>|  
|<span data-ttu-id="d5735-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="d5735-679">PRIMARY_KEY</span></span>|<span data-ttu-id="d5735-680">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-680">Boolean</span></span>|  
|<span data-ttu-id="d5735-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="d5735-681">UNIQUE</span></span>|<span data-ttu-id="d5735-682">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-682">Boolean</span></span>|  
|<span data-ttu-id="d5735-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="d5735-683">CLUSTERED</span></span>|<span data-ttu-id="d5735-684">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-684">Boolean</span></span>|  
|<span data-ttu-id="d5735-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="d5735-685">TYPE</span></span>|<span data-ttu-id="d5735-686">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-686">Int32</span></span>|  
|<span data-ttu-id="d5735-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="d5735-687">FILL_FACTOR</span></span>|<span data-ttu-id="d5735-688">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-688">Int32</span></span>|  
|<span data-ttu-id="d5735-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="d5735-689">INITIAL_SIZE</span></span>|<span data-ttu-id="d5735-690">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-690">Int32</span></span>|  
|<span data-ttu-id="d5735-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="d5735-691">NULLS</span></span>|<span data-ttu-id="d5735-692">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-692">Int32</span></span>|  
|<span data-ttu-id="d5735-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="d5735-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="d5735-694">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-694">Boolean</span></span>|  
|<span data-ttu-id="d5735-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="d5735-695">AUTO_UPDATE</span></span>|<span data-ttu-id="d5735-696">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-696">Boolean</span></span>|  
|<span data-ttu-id="d5735-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="d5735-697">NULL_COLLATION</span></span>|<span data-ttu-id="d5735-698">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-698">Int32</span></span>|  
|<span data-ttu-id="d5735-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="d5735-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="d5735-700">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-700">Int64</span></span>|  
|<span data-ttu-id="d5735-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d5735-701">COLUMN_NAME</span></span>|<span data-ttu-id="d5735-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-702">String</span></span>|  
|<span data-ttu-id="d5735-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-703">COLUMN_GUID</span></span>|<span data-ttu-id="d5735-704">GUID</span><span class="sxs-lookup"><span data-stu-id="d5735-704">Guid</span></span>|  
|<span data-ttu-id="d5735-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="d5735-705">COLUMN_PROPID</span></span>|<span data-ttu-id="d5735-706">Int64</span><span class="sxs-lookup"><span data-stu-id="d5735-706">Int64</span></span>|  
|<span data-ttu-id="d5735-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="d5735-707">COLLATION</span></span>|<span data-ttu-id="d5735-708">Int16</span><span class="sxs-lookup"><span data-stu-id="d5735-708">Int16</span></span>|  
|<span data-ttu-id="d5735-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="d5735-709">CARDINALITY</span></span>|<span data-ttu-id="d5735-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="d5735-710">Decimal</span></span>|  
|<span data-ttu-id="d5735-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="d5735-711">PAGES</span></span>|<span data-ttu-id="d5735-712">Int32</span><span class="sxs-lookup"><span data-stu-id="d5735-712">Int32</span></span>|  
|<span data-ttu-id="d5735-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="d5735-713">FILTER_CONDITION</span></span>|<span data-ttu-id="d5735-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d5735-714">String</span></span>|  
|<span data-ttu-id="d5735-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="d5735-715">INTEGRATED</span></span>|<span data-ttu-id="d5735-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="d5735-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5735-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5735-717">See also</span></span>

- [<span data-ttu-id="d5735-718">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="d5735-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
