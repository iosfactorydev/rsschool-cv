# Fedor Sukhovenko

## Contact Info

* email: **<ios.factory.dev@gmail.com>**
* discord: **Федор#3514**
* viber: **+375-29-685-31-44**

## Summary

I want to become an iOS developer, because i believe that Apple is the greatest company in the world!!!

## Skills



## Code examples

**It's not my code. This code is from project, where i work as a tester**

```
    public void addImageForIB(ArrayList vars) throws Exception {
        if ((vars.size() != 3) && ((vars.size() != 4))) {
            throw new Exception("addImage: Передано неверное число параметров");
        }
        try {
            int ownerID = Integer.parseInt(vars.get(0).toString());
            int imageType = Integer.parseInt(vars.get(1).toString());
            String imageString = vars.get(2).toString();
            int barsDocID = 0;
            if (vars.size() == 4) {
                barsDocID = Integer.parseInt(vars.get(3).toString());
            }
            OracleCallableStatement cs = (OracleCallableStatement) inset.
                    getConnection().prepareCall("{call p_ibank.insertImage(?,?,?,?)}");
            cs.setInt(1, ownerID);
            cs.registerOutParameter(2, OracleTypes.BLOB);
            cs.setInt(3, imageType);
            cs.setInt(4, barsDocID);
            java.io.ByteArrayOutputStream baos = new java.io.ByteArrayOutputStream();
            baos.write(imageString.getBytes());
            if (baos.size() > 0) {
                cs.execute();
                OutputStream os = cs.getBLOB(2).setBinaryStream(1L);
                os.write(baos.toByteArray());
                os.close();
            }
            cs.close();
        } catch (NumberFormatException e) {
            throw new Exception("Ошибка получения ID клиента");
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
```

## Experience

* software maintenance
* setting tasks for software development
* tasks testing

## Education

* Belarusian State University of Informatics and Radioelectronics

## English

* **A2** - Pre-Intermediate
