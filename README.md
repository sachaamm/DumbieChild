# DumbieChild
Dumbie child

```cs

void RemoveBlock()
    {
        int x = (int)ActionPointPos().x;
        int y = (int)ActionPointPos().y;
        int z = (int)ActionPointPos().z;

        Vector3 scale = indicatorPoint.transform.localScale;
        
        for(int _x = x; _x <  x + scale.x; _x++)
        {
            for (int _y = y; _y < y + scale.y; _y++)
            {
                for (int _z = z; _z < z + scale.z; _z++)
                {
                    int xAdd = _x - (int)scale.x / 2;
                    int yAdd = _y - (int)scale.y / 2;
                    int zAdd = _z - (int)scale.z / 2;

                    // Ajouter un block si il n'est pas déja présent à cette position
                    if (BlockExists(xAdd, yAdd, zAdd))
                    {
                        // si un bloc existe a ses coordonnees on le supprime

                        // Detruire le GameObject dans l'objet
                        GameObject blockGo = GameObject.Find(xAdd + "_" + yAdd + "_" + zAdd);

                        // Si blockGo existe on le detruit
                        if (blockGo) Destroy(blockGo);

                        Block block = GetBlockAt(new Vector3(xAdd, yAdd, zAdd));
                        blocks.Remove(block);

                    }
                }
            }

        }

        // Supprimer un block si il est présent à cette position
        

        // blocks.Remove
    }
```
