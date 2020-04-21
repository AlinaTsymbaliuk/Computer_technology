# Computer_technology
Project computers_technology
public class ResponseData {
    
    public Vector column_table_names = null;
    public Vector table_data = null;

    private DB_Helper db_helper = new DB_Helper();
    
    public ResponseData GetData()
    {
        String query = null;
        
          switch(Config.CURRENT_TABLE)
        {
            case "cars": 
                query = "SELECT id AS 'id_car', surname AS surname', namr AS 'name’, patronymic AS patronymic, acad_client AS 'academic client', position AS 'position', experience AS 'experience' FROM cars";
                break;
            case "rental_cars": 
                query = "SELECT id AS 'rental_car', name AS 'Name', type AS 'Type', hours AS 'Hours' FROM rental_cars";
                break;
            case "rental_car": 
                query = "SELECT id_car AS 'id_car', id_rental_car AS 'rental_car', group AS 'group' FROM rental_car";

                break;
        }        ResponseData data = db_helper.GetData(query);
        
        return data;
    }
}
