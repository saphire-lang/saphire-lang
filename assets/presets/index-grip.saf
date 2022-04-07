require "grip"

class IndexController < Grip::Controllers::Http
  def get(context : Context) : Context
    context
      .put_status(200) # Assign the status code to 200 OK.
      .json({"id" => 1}) # Respond with JSON content.
      .halt # Close the connection.
  end

  def index(context : Context) : Context
    id =
      context
        .fetch_path_params
        .["id"]

    # An optional secondary argument gives a custom `Content-Type` header to the response.
    context
      .json(content: {"id" => id}, content_type: "application/json; charset=us-ascii")
  end
end

class Application < Grip::Application
  def routes
    get "/", IndexController
    get "/:id", IndexController, as: :index
  end
end

app = Application.new
app.run