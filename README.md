# Sample simulator code for an ideal RMT chip

Sample JSONs provided in samples folder.

Run `python sim.py <filename>` to execute the script.

Every JSON entry must contain the fields: id, step, and match.

A match kind of "ternary" also requires entries and key_size fields. Note that we omit data_size for "ternary" because the amount of SRAM used to support the TCAM lookup is often negligible.

A match kind of "exact" also requires a method field. The method field must be either "index" or "hash." 

A "hash" method "exact" entry also requires the fields: entries, key_size, and data_size. The key_size and data_size are concatenated together and hashed. Assume a constant load factor of 0.8 (1.25 memory penalty).

An "index" method "exact" entry also requires the fields: key_size and data_size. Note that this lacks an entries field. An entries field is not needed because with a direct-indexed array, the key of length n is used to index into a 2^n array.
