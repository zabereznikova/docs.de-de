---
title: ODBC-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: ffe80120ceffbe29c0a117cf1194860c5782be8c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365905"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="872ed-102">ODBC-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="872ed-102">ODBC Schema Collections</span></span>

<span data-ttu-id="872ed-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Treiber für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="872ed-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>

## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="872ed-104">Microsoft SQL Server-ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="872ed-104">Microsoft SQL Server ODBC Driver</span></span>

<span data-ttu-id="872ed-105">Der Microsoft SQL Server-ODBC-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="872ed-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="872ed-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="872ed-106">Tables</span></span>

- <span data-ttu-id="872ed-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="872ed-107">Indexes</span></span>

- <span data-ttu-id="872ed-108">Columns</span><span class="sxs-lookup"><span data-stu-id="872ed-108">Columns</span></span>

- <span data-ttu-id="872ed-109">Verfahren</span><span class="sxs-lookup"><span data-stu-id="872ed-109">Procedures</span></span>

- <span data-ttu-id="872ed-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="872ed-110">ProcedureColumns</span></span>

- <span data-ttu-id="872ed-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="872ed-111">ProcedureParameters</span></span>

- <span data-ttu-id="872ed-112">Ansichten</span><span class="sxs-lookup"><span data-stu-id="872ed-112">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="872ed-113">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="872ed-113">Tables and Views</span></span>

|<span data-ttu-id="872ed-114">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-114">ColumnName</span></span>|<span data-ttu-id="872ed-115">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-115">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="872ed-116">TABLE_CAT</span></span>|<span data-ttu-id="872ed-117">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-117">String</span></span>|
|<span data-ttu-id="872ed-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="872ed-118">TABLE_SCHEM</span></span>|<span data-ttu-id="872ed-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-119">String</span></span>|
|<span data-ttu-id="872ed-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-120">TABLE_NAME</span></span>|<span data-ttu-id="872ed-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-121">String</span></span>|
|<span data-ttu-id="872ed-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-122">TABLE_TYPE</span></span>|<span data-ttu-id="872ed-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-123">String</span></span>|
|<span data-ttu-id="872ed-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-124">REMARKS</span></span>|<span data-ttu-id="872ed-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-125">String</span></span>|

### <a name="indexes"></a><span data-ttu-id="872ed-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="872ed-126">Indexes</span></span>

|<span data-ttu-id="872ed-127">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-127">ColumnName</span></span>|<span data-ttu-id="872ed-128">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-128">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="872ed-129">TABLE_CAT</span></span>|<span data-ttu-id="872ed-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-130">String</span></span>|
|<span data-ttu-id="872ed-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="872ed-131">TABLE_SCHEM</span></span>|<span data-ttu-id="872ed-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-132">String</span></span>|
|<span data-ttu-id="872ed-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-133">TABLE_NAME</span></span>|<span data-ttu-id="872ed-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-134">String</span></span>|
|<span data-ttu-id="872ed-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="872ed-135">NON_UNIQUE</span></span>|<span data-ttu-id="872ed-136">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-136">Int16</span></span>|
|<span data-ttu-id="872ed-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="872ed-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="872ed-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-138">String</span></span>|
|<span data-ttu-id="872ed-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-139">INDEX_NAME</span></span>|<span data-ttu-id="872ed-140">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-140">String</span></span>|
|<span data-ttu-id="872ed-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-141">TYPE</span></span>|<span data-ttu-id="872ed-142">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-142">Int16</span></span>|
|<span data-ttu-id="872ed-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="872ed-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="872ed-144">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-144">Int16</span></span>|
|<span data-ttu-id="872ed-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-145">COLUMN_NAME</span></span>|<span data-ttu-id="872ed-146">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-146">String</span></span>|
|<span data-ttu-id="872ed-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="872ed-147">ASC_OR_DESC</span></span>|<span data-ttu-id="872ed-148">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-148">String</span></span>|
|<span data-ttu-id="872ed-149">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="872ed-149">CARDINALITY</span></span>|<span data-ttu-id="872ed-150">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-150">Int32</span></span>|
|<span data-ttu-id="872ed-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="872ed-151">PAGES</span></span>|<span data-ttu-id="872ed-152">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-152">Int32</span></span>|
|<span data-ttu-id="872ed-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="872ed-153">FILTER_CONDITION</span></span>|<span data-ttu-id="872ed-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-154">String</span></span>|
|<span data-ttu-id="872ed-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="872ed-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="872ed-156">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-156">String</span></span>|
|<span data-ttu-id="872ed-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="872ed-158">Byte</span><span class="sxs-lookup"><span data-stu-id="872ed-158">Byte</span></span>|

### <a name="columns"></a><span data-ttu-id="872ed-159">Columns</span><span class="sxs-lookup"><span data-stu-id="872ed-159">Columns</span></span>

|<span data-ttu-id="872ed-160">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-160">ColumnName</span></span>|<span data-ttu-id="872ed-161">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-161">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="872ed-162">TABLE_CAT</span></span>|<span data-ttu-id="872ed-163">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-163">String</span></span>|
|<span data-ttu-id="872ed-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="872ed-164">TABLE_SCHEM</span></span>|<span data-ttu-id="872ed-165">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-165">String</span></span>|
|<span data-ttu-id="872ed-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-166">TABLE_NAME</span></span>|<span data-ttu-id="872ed-167">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-167">String</span></span>|
|<span data-ttu-id="872ed-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-168">COLUMN_NAME</span></span>|<span data-ttu-id="872ed-169">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-169">String</span></span>|
|<span data-ttu-id="872ed-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-170">DATA_TYPE</span></span>|<span data-ttu-id="872ed-171">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-171">Int16</span></span>|
|<span data-ttu-id="872ed-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-172">TYPE_NAME</span></span>|<span data-ttu-id="872ed-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-173">String</span></span>|
|<span data-ttu-id="872ed-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="872ed-174">COLUMN_SIZE</span></span>|<span data-ttu-id="872ed-175">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-175">Int32</span></span>|
|<span data-ttu-id="872ed-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="872ed-177">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-177">Int32</span></span>|
|<span data-ttu-id="872ed-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="872ed-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="872ed-179">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-179">Int16</span></span>|
|<span data-ttu-id="872ed-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="872ed-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="872ed-181">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-181">Int16</span></span>|
|<span data-ttu-id="872ed-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-182">NULLABLE</span></span>|<span data-ttu-id="872ed-183">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-183">Int16</span></span>|
|<span data-ttu-id="872ed-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-184">REMARKS</span></span>|<span data-ttu-id="872ed-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-185">String</span></span>|
|<span data-ttu-id="872ed-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="872ed-186">COLUMN_DEF</span></span>|<span data-ttu-id="872ed-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-187">String</span></span>|
|<span data-ttu-id="872ed-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="872ed-189">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-189">Int16</span></span>|
|<span data-ttu-id="872ed-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="872ed-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="872ed-191">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-191">Int16</span></span>|
|<span data-ttu-id="872ed-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="872ed-193">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-193">Int32</span></span>|
|<span data-ttu-id="872ed-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="872ed-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="872ed-195">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-195">Int32</span></span>|
|<span data-ttu-id="872ed-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-196">IS_NULLABLE</span></span>|<span data-ttu-id="872ed-197">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-197">String</span></span>|
|<span data-ttu-id="872ed-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="872ed-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="872ed-199">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-199">String</span></span>|
|<span data-ttu-id="872ed-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="872ed-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="872ed-201">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-201">String</span></span>|
|<span data-ttu-id="872ed-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="872ed-203">Byte</span><span class="sxs-lookup"><span data-stu-id="872ed-203">Byte</span></span>|

### <a name="procedures"></a><span data-ttu-id="872ed-204">Verfahren</span><span class="sxs-lookup"><span data-stu-id="872ed-204">Procedures</span></span>

|<span data-ttu-id="872ed-205">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-205">ColumnName</span></span>|<span data-ttu-id="872ed-206">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-206">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="872ed-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="872ed-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-208">String</span></span>|
|<span data-ttu-id="872ed-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="872ed-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="872ed-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-210">String</span></span>|
|<span data-ttu-id="872ed-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="872ed-212">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-212">String</span></span>|
|<span data-ttu-id="872ed-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="872ed-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="872ed-214">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-214">Int32</span></span>|
|<span data-ttu-id="872ed-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="872ed-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="872ed-216">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-216">Int32</span></span>|
|<span data-ttu-id="872ed-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="872ed-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="872ed-218">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-218">Int32</span></span>|
|<span data-ttu-id="872ed-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-219">REMARKS</span></span>|<span data-ttu-id="872ed-220">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-220">String</span></span>|
|<span data-ttu-id="872ed-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="872ed-222">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-222">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="872ed-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="872ed-223">ProcedureColumns</span></span>

|<span data-ttu-id="872ed-224">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-224">ColumnName</span></span>|<span data-ttu-id="872ed-225">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-225">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="872ed-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="872ed-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-227">String</span></span>|
|<span data-ttu-id="872ed-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="872ed-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="872ed-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-229">String</span></span>|
|<span data-ttu-id="872ed-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="872ed-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-231">String</span></span>|
|<span data-ttu-id="872ed-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-232">COLUMN_NAME</span></span>|<span data-ttu-id="872ed-233">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-233">String</span></span>|
|<span data-ttu-id="872ed-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-234">COLUMN_TYPE</span></span>|<span data-ttu-id="872ed-235">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-235">Int16</span></span>|
|<span data-ttu-id="872ed-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-236">DATA_TYPE</span></span>|<span data-ttu-id="872ed-237">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-237">Int16</span></span>|
|<span data-ttu-id="872ed-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-238">TYPE_NAME</span></span>|<span data-ttu-id="872ed-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-239">String</span></span>|
|<span data-ttu-id="872ed-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="872ed-240">COLUMN_SIZE</span></span>|<span data-ttu-id="872ed-241">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-241">Int32</span></span>|
|<span data-ttu-id="872ed-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="872ed-243">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-243">Int32</span></span>|
|<span data-ttu-id="872ed-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="872ed-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="872ed-245">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-245">Int16</span></span>|
|<span data-ttu-id="872ed-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="872ed-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="872ed-247">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-247">Int16</span></span>|
|<span data-ttu-id="872ed-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-248">NULLABLE</span></span>|<span data-ttu-id="872ed-249">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-249">Int16</span></span>|
|<span data-ttu-id="872ed-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-250">REMARKS</span></span>|<span data-ttu-id="872ed-251">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-251">String</span></span>|
|<span data-ttu-id="872ed-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="872ed-252">COLUMN_DEF</span></span>|<span data-ttu-id="872ed-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-253">String</span></span>|
|<span data-ttu-id="872ed-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="872ed-255">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-255">Int16</span></span>|
|<span data-ttu-id="872ed-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="872ed-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="872ed-257">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-257">Int16</span></span>|
|<span data-ttu-id="872ed-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="872ed-259">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-259">Int32</span></span>|
|<span data-ttu-id="872ed-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="872ed-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="872ed-261">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-261">Int32</span></span>|
|<span data-ttu-id="872ed-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-262">IS_NULLABLE</span></span>|<span data-ttu-id="872ed-263">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-263">String</span></span>|
|<span data-ttu-id="872ed-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="872ed-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="872ed-265">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-265">String</span></span>|
|<span data-ttu-id="872ed-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="872ed-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="872ed-267">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-267">String</span></span>|
|<span data-ttu-id="872ed-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="872ed-269">Byte</span><span class="sxs-lookup"><span data-stu-id="872ed-269">Byte</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="872ed-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="872ed-270">ProcedureParameters</span></span>

|<span data-ttu-id="872ed-271">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-271">ColumnName</span></span>|<span data-ttu-id="872ed-272">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-272">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="872ed-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="872ed-274">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-274">String</span></span>|
|<span data-ttu-id="872ed-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="872ed-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="872ed-276">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-276">String</span></span>|
|<span data-ttu-id="872ed-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="872ed-278">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-278">String</span></span>|
|<span data-ttu-id="872ed-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-279">COLUMN_NAME</span></span>|<span data-ttu-id="872ed-280">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-280">String</span></span>|
|<span data-ttu-id="872ed-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-281">COLUMN_TYPE</span></span>|<span data-ttu-id="872ed-282">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-282">Int16</span></span>|
|<span data-ttu-id="872ed-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-283">DATA_TYPE</span></span>|<span data-ttu-id="872ed-284">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-284">Int16</span></span>|
|<span data-ttu-id="872ed-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-285">TYPE_NAME</span></span>|<span data-ttu-id="872ed-286">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-286">String</span></span>|
|<span data-ttu-id="872ed-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="872ed-287">COLUMN_SIZE</span></span>|<span data-ttu-id="872ed-288">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-288">Int32</span></span>|
|<span data-ttu-id="872ed-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="872ed-290">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-290">Int32</span></span>|
|<span data-ttu-id="872ed-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="872ed-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="872ed-292">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-292">Int16</span></span>|
|<span data-ttu-id="872ed-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="872ed-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="872ed-294">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-294">Int16</span></span>|
|<span data-ttu-id="872ed-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-295">NULLABLE</span></span>|<span data-ttu-id="872ed-296">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-296">Int16</span></span>|
|<span data-ttu-id="872ed-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-297">REMARKS</span></span>|<span data-ttu-id="872ed-298">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-298">String</span></span>|
|<span data-ttu-id="872ed-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="872ed-299">COLUMN_DEF</span></span>|<span data-ttu-id="872ed-300">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-300">String</span></span>|
|<span data-ttu-id="872ed-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="872ed-302">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-302">Int16</span></span>|
|<span data-ttu-id="872ed-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="872ed-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="872ed-304">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-304">Int16</span></span>|
|<span data-ttu-id="872ed-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="872ed-306">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-306">Int32</span></span>|
|<span data-ttu-id="872ed-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="872ed-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="872ed-308">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-308">Int32</span></span>|
|<span data-ttu-id="872ed-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-309">IS_NULLABLE</span></span>|<span data-ttu-id="872ed-310">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-310">String</span></span>|
|<span data-ttu-id="872ed-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="872ed-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="872ed-312">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-312">String</span></span>|
|<span data-ttu-id="872ed-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="872ed-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="872ed-314">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-314">String</span></span>|
|<span data-ttu-id="872ed-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="872ed-316">Byte</span><span class="sxs-lookup"><span data-stu-id="872ed-316">Byte</span></span>|

## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="872ed-317">Microsoft Oracle ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="872ed-317">Microsoft Oracle ODBC Driver</span></span>

<span data-ttu-id="872ed-318">Der Microsoft SQL Server Oracle ODBC-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="872ed-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="872ed-319">Tabellen</span><span class="sxs-lookup"><span data-stu-id="872ed-319">Tables</span></span>

- <span data-ttu-id="872ed-320">Columns</span><span class="sxs-lookup"><span data-stu-id="872ed-320">Columns</span></span>

- <span data-ttu-id="872ed-321">Verfahren</span><span class="sxs-lookup"><span data-stu-id="872ed-321">Procedures</span></span>

- <span data-ttu-id="872ed-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="872ed-322">ProcedureColumns</span></span>

- <span data-ttu-id="872ed-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="872ed-323">ProcedureParameters</span></span>

- <span data-ttu-id="872ed-324">Ansichten</span><span class="sxs-lookup"><span data-stu-id="872ed-324">Views</span></span>

- <span data-ttu-id="872ed-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="872ed-325">Indexes</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="872ed-326">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="872ed-326">Tables and Views</span></span>

|<span data-ttu-id="872ed-327">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-327">ColumnName</span></span>|<span data-ttu-id="872ed-328">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-328">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="872ed-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="872ed-330">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-330">String</span></span>|
|<span data-ttu-id="872ed-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="872ed-331">TABLE_OWNER</span></span>|<span data-ttu-id="872ed-332">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-332">String</span></span>|
|<span data-ttu-id="872ed-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-333">TABLE_NAME</span></span>|<span data-ttu-id="872ed-334">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-334">String</span></span>|
|<span data-ttu-id="872ed-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-335">TABLE_TYPE</span></span>|<span data-ttu-id="872ed-336">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-336">String</span></span>|
|<span data-ttu-id="872ed-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-337">REMARKS</span></span>|<span data-ttu-id="872ed-338">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-338">String</span></span>|

### <a name="columns"></a><span data-ttu-id="872ed-339">Columns</span><span class="sxs-lookup"><span data-stu-id="872ed-339">Columns</span></span>

|<span data-ttu-id="872ed-340">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-340">ColumnName</span></span>|<span data-ttu-id="872ed-341">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-341">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="872ed-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="872ed-343">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-343">String</span></span>|
|<span data-ttu-id="872ed-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="872ed-344">TABLE_OWNER</span></span>|<span data-ttu-id="872ed-345">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-345">String</span></span>|
|<span data-ttu-id="872ed-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-346">TABLE_NAME</span></span>|<span data-ttu-id="872ed-347">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-347">String</span></span>|
|<span data-ttu-id="872ed-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-348">COLUMN_NAME</span></span>|<span data-ttu-id="872ed-349">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-349">String</span></span>|
|<span data-ttu-id="872ed-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-350">DATA_TYPE</span></span>|<span data-ttu-id="872ed-351">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-351">Int16</span></span>|
|<span data-ttu-id="872ed-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-352">TYPE_NAME</span></span>|<span data-ttu-id="872ed-353">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-353">String</span></span>|
|<span data-ttu-id="872ed-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="872ed-354">PRECISION</span></span>|<span data-ttu-id="872ed-355">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-355">Int32</span></span>|
|<span data-ttu-id="872ed-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-356">LENGTH</span></span>|<span data-ttu-id="872ed-357">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-357">Int32</span></span>|
|<span data-ttu-id="872ed-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="872ed-358">SCALE</span></span>|<span data-ttu-id="872ed-359">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-359">Int16</span></span>|
|<span data-ttu-id="872ed-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="872ed-360">RADIX</span></span>|<span data-ttu-id="872ed-361">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-361">Int16</span></span>|
|<span data-ttu-id="872ed-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-362">NULLABLE</span></span>|<span data-ttu-id="872ed-363">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-363">Int16</span></span>|
|<span data-ttu-id="872ed-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-364">REMARKS</span></span>|<span data-ttu-id="872ed-365">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-365">String</span></span>|
|<span data-ttu-id="872ed-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="872ed-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="872ed-367">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-367">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="872ed-368">Verfahren</span><span class="sxs-lookup"><span data-stu-id="872ed-368">Procedures</span></span>

|<span data-ttu-id="872ed-369">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-369">ColumnName</span></span>|<span data-ttu-id="872ed-370">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-370">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="872ed-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="872ed-372">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-372">String</span></span>|
|<span data-ttu-id="872ed-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="872ed-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="872ed-374">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-374">String</span></span>|
|<span data-ttu-id="872ed-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="872ed-376">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-376">String</span></span>|
|<span data-ttu-id="872ed-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="872ed-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="872ed-378">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-378">Int16</span></span>|
|<span data-ttu-id="872ed-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="872ed-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="872ed-380">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-380">Int16</span></span>|
|<span data-ttu-id="872ed-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="872ed-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="872ed-382">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-382">Int16</span></span>|
|<span data-ttu-id="872ed-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-383">REMARKS</span></span>|<span data-ttu-id="872ed-384">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-384">String</span></span>|
|<span data-ttu-id="872ed-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="872ed-386">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-386">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="872ed-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="872ed-387">ProcedureColumns</span></span>

|<span data-ttu-id="872ed-388">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-388">ColumnName</span></span>|<span data-ttu-id="872ed-389">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-389">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="872ed-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="872ed-391">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-391">String</span></span>|
|<span data-ttu-id="872ed-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="872ed-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="872ed-393">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-393">String</span></span>|
|<span data-ttu-id="872ed-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="872ed-395">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-395">String</span></span>|
|<span data-ttu-id="872ed-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-396">COLUMN_NAME</span></span>|<span data-ttu-id="872ed-397">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-397">String</span></span>|
|<span data-ttu-id="872ed-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-398">COLUMN_TYPE</span></span>|<span data-ttu-id="872ed-399">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-399">Int16</span></span>|
|<span data-ttu-id="872ed-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-400">DATA_TYPE</span></span>|<span data-ttu-id="872ed-401">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-401">Int16</span></span>|
|<span data-ttu-id="872ed-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-402">TYPE_NAME</span></span>|<span data-ttu-id="872ed-403">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-403">String</span></span>|
|<span data-ttu-id="872ed-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="872ed-404">PRECISION</span></span>|<span data-ttu-id="872ed-405">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-405">Int32</span></span>|
|<span data-ttu-id="872ed-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-406">LENGTH</span></span>|<span data-ttu-id="872ed-407">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-407">Int32</span></span>|
|<span data-ttu-id="872ed-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="872ed-408">SCALE</span></span>|<span data-ttu-id="872ed-409">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-409">Int16</span></span>|
|<span data-ttu-id="872ed-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="872ed-410">RADIX</span></span>|<span data-ttu-id="872ed-411">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-411">Int16</span></span>|
|<span data-ttu-id="872ed-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-412">NULLABLE</span></span>|<span data-ttu-id="872ed-413">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-413">Int16</span></span>|
|<span data-ttu-id="872ed-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-414">REMARKS</span></span>|<span data-ttu-id="872ed-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-415">String</span></span>|
|<span data-ttu-id="872ed-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="872ed-416">OVERLOAD</span></span>|<span data-ttu-id="872ed-417">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-417">Int32</span></span>|
|<span data-ttu-id="872ed-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="872ed-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="872ed-419">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-419">Int32</span></span>|

## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="872ed-420">Microsoft Jet ODBC-Treiber</span><span class="sxs-lookup"><span data-stu-id="872ed-420">Microsoft Jet ODBC Driver</span></span>

<span data-ttu-id="872ed-421">Der Microsoft Jet ODBC-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="872ed-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>

- <span data-ttu-id="872ed-422">Tabellen</span><span class="sxs-lookup"><span data-stu-id="872ed-422">Tables</span></span>

- <span data-ttu-id="872ed-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="872ed-423">Indexes</span></span>

- <span data-ttu-id="872ed-424">Columns</span><span class="sxs-lookup"><span data-stu-id="872ed-424">Columns</span></span>

- <span data-ttu-id="872ed-425">Verfahren</span><span class="sxs-lookup"><span data-stu-id="872ed-425">Procedures</span></span>

- <span data-ttu-id="872ed-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="872ed-426">ProcedureColumns</span></span>

- <span data-ttu-id="872ed-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="872ed-427">ProcedureParameters</span></span>

- <span data-ttu-id="872ed-428">Ansichten</span><span class="sxs-lookup"><span data-stu-id="872ed-428">Views</span></span>

### <a name="tables-and-views"></a><span data-ttu-id="872ed-429">Tables und Views</span><span class="sxs-lookup"><span data-stu-id="872ed-429">Tables and Views</span></span>

|<span data-ttu-id="872ed-430">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-430">ColumnName</span></span>|<span data-ttu-id="872ed-431">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-431">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="872ed-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="872ed-433">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-433">String</span></span>|
|<span data-ttu-id="872ed-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="872ed-434">TABLE_OWNER</span></span>|<span data-ttu-id="872ed-435">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-435">String</span></span>|
|<span data-ttu-id="872ed-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-436">TABLE_NAME</span></span>|<span data-ttu-id="872ed-437">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-437">String</span></span>|
|<span data-ttu-id="872ed-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-438">TABLE_TYPE</span></span>|<span data-ttu-id="872ed-439">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-439">String</span></span>|
|<span data-ttu-id="872ed-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-440">REMARKS</span></span>|<span data-ttu-id="872ed-441">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-441">String</span></span>|

### <a name="columns"></a><span data-ttu-id="872ed-442">Columns</span><span class="sxs-lookup"><span data-stu-id="872ed-442">Columns</span></span>

|<span data-ttu-id="872ed-443">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-443">ColumnName</span></span>|<span data-ttu-id="872ed-444">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-444">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="872ed-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="872ed-446">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-446">String</span></span>|
|<span data-ttu-id="872ed-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="872ed-447">TABLE_OWNER</span></span>|<span data-ttu-id="872ed-448">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-448">String</span></span>|
|<span data-ttu-id="872ed-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-449">TABLE_NAME</span></span>|<span data-ttu-id="872ed-450">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-450">String</span></span>|
|<span data-ttu-id="872ed-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-451">COLUMN_NAME</span></span>|<span data-ttu-id="872ed-452">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-452">String</span></span>|
|<span data-ttu-id="872ed-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-453">DATA_TYPE</span></span>|<span data-ttu-id="872ed-454">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-454">Int16</span></span>|
|<span data-ttu-id="872ed-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-455">TYPE_NAME</span></span>|<span data-ttu-id="872ed-456">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-456">String</span></span>|
|<span data-ttu-id="872ed-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="872ed-457">PRECISION</span></span>|<span data-ttu-id="872ed-458">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-458">Int32</span></span>|
|<span data-ttu-id="872ed-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-459">LENGTH</span></span>|<span data-ttu-id="872ed-460">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-460">Int32</span></span>|
|<span data-ttu-id="872ed-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="872ed-461">SCALE</span></span>|<span data-ttu-id="872ed-462">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-462">Int16</span></span>|
|<span data-ttu-id="872ed-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="872ed-463">RADIX</span></span>|<span data-ttu-id="872ed-464">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-464">Int16</span></span>|
|<span data-ttu-id="872ed-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-465">NULLABLE</span></span>|<span data-ttu-id="872ed-466">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-466">Int16</span></span>|
|<span data-ttu-id="872ed-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-467">REMARKS</span></span>|<span data-ttu-id="872ed-468">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-468">String</span></span>|
|<span data-ttu-id="872ed-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="872ed-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="872ed-470">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-470">Int32</span></span>|

### <a name="procedures"></a><span data-ttu-id="872ed-471">Verfahren</span><span class="sxs-lookup"><span data-stu-id="872ed-471">Procedures</span></span>

|<span data-ttu-id="872ed-472">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-472">ColumnName</span></span>|<span data-ttu-id="872ed-473">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-473">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="872ed-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="872ed-475">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-475">String</span></span>|
|<span data-ttu-id="872ed-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="872ed-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="872ed-477">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-477">String</span></span>|
|<span data-ttu-id="872ed-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="872ed-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-479">String</span></span>|
|<span data-ttu-id="872ed-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="872ed-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="872ed-481">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-481">Int16</span></span>|
|<span data-ttu-id="872ed-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="872ed-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="872ed-483">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-483">Int16</span></span>|
|<span data-ttu-id="872ed-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="872ed-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="872ed-485">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-485">Int16</span></span>|
|<span data-ttu-id="872ed-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-486">REMARKS</span></span>|<span data-ttu-id="872ed-487">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-487">String</span></span>|
|<span data-ttu-id="872ed-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="872ed-489">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-489">Int16</span></span>|

### <a name="procedurecolumns"></a><span data-ttu-id="872ed-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="872ed-490">ProcedureColumns</span></span>

|<span data-ttu-id="872ed-491">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-491">ColumnName</span></span>|<span data-ttu-id="872ed-492">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-492">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="872ed-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="872ed-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-494">String</span></span>|
|<span data-ttu-id="872ed-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="872ed-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="872ed-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-496">String</span></span>|
|<span data-ttu-id="872ed-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="872ed-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-498">String</span></span>|
|<span data-ttu-id="872ed-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-499">COLUMN_NAME</span></span>|<span data-ttu-id="872ed-500">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-500">String</span></span>|
|<span data-ttu-id="872ed-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-501">COLUMN_TYPE</span></span>|<span data-ttu-id="872ed-502">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-502">Int16</span></span>|
|<span data-ttu-id="872ed-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-503">DATA_TYPE</span></span>|<span data-ttu-id="872ed-504">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-504">Int16</span></span>|
|<span data-ttu-id="872ed-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-505">TYPE_NAME</span></span>|<span data-ttu-id="872ed-506">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-506">String</span></span>|
|<span data-ttu-id="872ed-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="872ed-507">PRECISION</span></span>|<span data-ttu-id="872ed-508">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-508">Int32</span></span>|
|<span data-ttu-id="872ed-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-509">LENGTH</span></span>|<span data-ttu-id="872ed-510">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-510">Int32</span></span>|
|<span data-ttu-id="872ed-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="872ed-511">SCALE</span></span>|<span data-ttu-id="872ed-512">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-512">Int16</span></span>|
|<span data-ttu-id="872ed-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="872ed-513">RADIX</span></span>|<span data-ttu-id="872ed-514">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-514">Int16</span></span>|
|<span data-ttu-id="872ed-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-515">NULLABLE</span></span>|<span data-ttu-id="872ed-516">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-516">Int16</span></span>|
|<span data-ttu-id="872ed-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-517">REMARKS</span></span>|<span data-ttu-id="872ed-518">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-518">String</span></span>|
|<span data-ttu-id="872ed-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="872ed-519">OVERLOAD</span></span>|<span data-ttu-id="872ed-520">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-520">Int32</span></span>|
|<span data-ttu-id="872ed-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="872ed-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="872ed-522">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-522">Int32</span></span>|

### <a name="procedureparameters"></a><span data-ttu-id="872ed-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="872ed-523">ProcedureParameters</span></span>

|<span data-ttu-id="872ed-524">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="872ed-524">ColumnName</span></span>|<span data-ttu-id="872ed-525">DataType</span><span class="sxs-lookup"><span data-stu-id="872ed-525">DataType</span></span>|
|----------------|--------------|
|<span data-ttu-id="872ed-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="872ed-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="872ed-527">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-527">String</span></span>|
|<span data-ttu-id="872ed-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="872ed-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="872ed-529">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-529">String</span></span>|
|<span data-ttu-id="872ed-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="872ed-531">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-531">String</span></span>|
|<span data-ttu-id="872ed-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-532">COLUMN_NAME</span></span>|<span data-ttu-id="872ed-533">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-533">String</span></span>|
|<span data-ttu-id="872ed-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-534">COLUMN_TYPE</span></span>|<span data-ttu-id="872ed-535">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-535">Int16</span></span>|
|<span data-ttu-id="872ed-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-536">DATA_TYPE</span></span>|<span data-ttu-id="872ed-537">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-537">Int16</span></span>|
|<span data-ttu-id="872ed-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="872ed-538">TYPE_NAME</span></span>|<span data-ttu-id="872ed-539">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-539">String</span></span>|
|<span data-ttu-id="872ed-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="872ed-540">COLUMN_SIZE</span></span>|<span data-ttu-id="872ed-541">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-541">Int32</span></span>|
|<span data-ttu-id="872ed-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="872ed-543">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-543">Int32</span></span>|
|<span data-ttu-id="872ed-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="872ed-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="872ed-545">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-545">Int16</span></span>|
|<span data-ttu-id="872ed-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="872ed-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="872ed-547">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-547">Int16</span></span>|
|<span data-ttu-id="872ed-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-548">NULLABLE</span></span>|<span data-ttu-id="872ed-549">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-549">Int16</span></span>|
|<span data-ttu-id="872ed-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="872ed-550">REMARKS</span></span>|<span data-ttu-id="872ed-551">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-551">String</span></span>|
|<span data-ttu-id="872ed-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="872ed-552">COLUMN_DEF</span></span>|<span data-ttu-id="872ed-553">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-553">String</span></span>|
|<span data-ttu-id="872ed-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="872ed-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="872ed-555">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-555">Int16</span></span>|
|<span data-ttu-id="872ed-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="872ed-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="872ed-557">Int16</span><span class="sxs-lookup"><span data-stu-id="872ed-557">Int16</span></span>|
|<span data-ttu-id="872ed-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="872ed-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="872ed-559">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-559">Int32</span></span>|
|<span data-ttu-id="872ed-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="872ed-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="872ed-561">Int32</span><span class="sxs-lookup"><span data-stu-id="872ed-561">Int32</span></span>|
|<span data-ttu-id="872ed-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="872ed-562">IS_NULLABLE</span></span>|<span data-ttu-id="872ed-563">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="872ed-563">String</span></span>|

## <a name="see-also"></a><span data-ttu-id="872ed-564">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="872ed-564">See also</span></span>

- [<span data-ttu-id="872ed-565">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="872ed-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
